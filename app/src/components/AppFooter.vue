<template>
	<footer class="footer">
		<div class="footer__header">
			<div class="footer__header--left">
				<p>KITO</p>
			</div>
			<div class="footer__header--right">
				<div class="content">
					<p>Join our list and get 20% off your first purchase!</p>
					<div class="input">
						<b-input-group class="mb-3">
							<b-form-input placeholder="Enter you email" v-model="emailInput"></b-form-input>
							<b-input-group-append>
								<b-button class="sub-btn" size="sm">SUBSCRIBE</b-button>
							</b-input-group-append>
						</b-input-group>
					</div>
				</div>
			</div>
		</div>
		<div class="line first-line"></div>
		<div class="footer__body">
			<div class="footer__body--option" v-for="term in terms" :key="term.title">
				<div class="title">{{ term.title }}</div>
				<div class="terms">
					<div class="terms--item btn" v-for="item in term.items" :key="item.icon">
						<font-awesome-icon v-if="item.icon" :icon="[item.brand ? 'fab' : 'fas', item.icon]" />
						{{ item.context }}
					</div>
				</div>
			</div>
			<!-- <div class="footer__body--option"></div> -->
		</div>
		<div class="line last-line"></div>
		<p class="footer__lastword">Beae's template © 2022. All Rights Reserved.</p>
	</footer>
</template>

<script>
export default {
	name: 'app-footer',
	data() {
		return {
			terms: [
				{
					title: 'Contact Info',
					items: [
						{
							icon: 'location-dot',
							context: '560 King St W, Kingston, ON K7L 4V7, Canada',
						},
						{
							icon: 'envelope',
							context: 'contactinfo@gmail.com',
						},
						{
							icon: 'headphones',
							context: '+1 212 736 3100',
						},
					],
				},
				{
					title: 'Quick Links',
					items: [
						{
							context: 'My account',
						},

						{
							context: 'Cart',
						},
						{
							context: 'Wishlist',
						},
						{
							context: 'Product Compare',
						},
					],
				},
				{
					title: 'Informations',
					items: [
						{
							context: 'Privacy Policy',
						},

						{
							context: 'Refund Policy',
						},
						{
							context: 'Shipping & return',
						},
						{
							context: 'Terms & Conditions',
						},
					],
				},
				{
					title: 'Follow us',
					items: [
						{
							brand: true,
							icon: 'facebook',
							context: 'Facebook',
						},

						{
							brand: true,
							icon: 'twitter',
							context: 'Twitter',
						},
						{
							brand: true,
							icon: 'instagram',
							context: 'Instagram',
						},
						{
							brand: true,
							icon: 'youtube',
							context: 'Youtube',
						},
					],
				},
			],
			emailInput: '',
		};
	},
};
</script>

<style scoped lang="scss">
@import '../assets/scss/variables.scss';

.footer {
	padding: 0 255px;
	width: 100%;
	margin-bottom: 27px;

	&__header {
		display: flex;
		justify-content: space-between;
		align-items: center;
		&--left {
			p {
				font-size: 24px;
				font-weight: 700;
				color: $text-color;
				text-align: center;
				font-family: Sansita;
				font-size: 54px;
				font-style: normal;
				font-weight: 800;
				line-height: 70px; /* 129.63% */
				text-transform: uppercase;
			}
		}
		&--right {
			text-align: right;
			.content {
				display: flex;
				p {
					text-align: left;
					max-width: 200px;
					font-family: Open Sans;
					font-size: 15px;
					font-weight: 700;
					line-height: 22px;
					margin: 0;
				}
				.input {
					/deep/.form-control {
						border: 1px solid $pink-color;
						height: 100%;
					}
					/deep/.input-group-append {
						background-color: $pink-color;
						border-radius: 10px;
						.btn-secondary {
							background-color: $pink-color;
							border: 1px solid $pink-color;
						}
					}

					.sub-btn {
						font-family: Open Sans;
						font-size: 17px;
						font-weight: 700;
						padding: 0 30px;
						line-height: 27px;
						letter-spacing: 1.7px;
					}
				}
			}
		}
	}
	.line {
		margin: 70px 0;
		width: 100%;
		border-top: 1px solid $text-color;
		opacity: 0.1;
	}
	.last-line {
		margin-bottom: 27px;
	}
	&__body {
		width: 100%;
		display: grid;
		grid-template-columns: repeat(4, 1fr);
		gap: 10px;
		&--option {
			justify-self: start;
			display: flex;
			flex-direction: column;
			align-items: start;
			.title {
				font-family: Sansita;
				font-size: 24px;
				font-style: normal;
				font-weight: 700;
				line-height: 31px;
				margin-bottom: 30px;
			}
			.terms {
				display: flex;
				flex-direction: column;
				align-items: start;
				row-gap: 20px;
				&--item {
					text-align: left;
					display: flex;
					:first-child {
						margin-right: 20px;
					}
				}
			}
		}
	}
	&__lastword {
		margin: 0;
		font-family: Open Sans;
		font-size: 15px;
		font-weight: 400;
		line-height: 26px;
	}
}

@media screen and (max-width: 1700px) {
	.footer {
		padding: 0 150px;
	}
}
@media screen and (max-width: 480px) {
	.footer {
		padding: 0 10px;
		&__header {
			flex-direction: column;
			&--right {
				.content {
					p {
						max-width: 100%;
					}
					align-items: center;
					flex-direction: column;
				}
			}
		}
		.first-line {
			display: none;
		}
		&__body {
			grid-template-columns: repeat(1, 1fr);
			gap: 40px;
			&--option {
				.title {
					margin-bottom: 20px;
				}
				.terms {
					row-gap: 15px;
				}
			}
		}
	}
}
</style>
