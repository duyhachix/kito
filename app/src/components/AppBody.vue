<template>
	<div class="body">
		<div class="body__title">
			<p>About Us</p>
			<div class="body__title--option">
				<h6>Home</h6>
				<div class="vertical-line"></div>
				<h6>About</h6>
			</div>
		</div>
		<div class="body__cta section">
			<div class="body__cta--left">
				<p class="about">ABOUT US</p>
				<h1 class="quote">Bring Exciting Moments of Fun While Playing & Learning For Children.</h1>
				<h4 class="contact">CONTACT US</h4>
			</div>
			<div class="body__cta--right">
				<div class="video">
					<b-embed type="video" aspect="4by3" controls>
						<source src="../assets/video/mountain.mp4" type="video/mp4" />
					</b-embed>
				</div>
			</div>
		</div>
		<div class="body__proud section">
			<div class="body__proud--title mid-section">
				<p>{{ proudTitle }}</p>
			</div>
			<div class="body__proud--cardGroup">
				<b-card tag="article" class="card" v-for="card in proudCards" :key="card.title">
					<b-card-text>
						<h2>{{ card.stat }}</h2>
						<h3>{{ card.title }}</h3>
						{{ card.context }}
					</b-card-text>
				</b-card>
			</div>
		</div>
		<div class="body__about section">
			<div class="body__about--left">
				<div class="left__image img__section">
					<img class="image" src="@/assets/left_img.jpeg" alt="" />
				</div>
				<div class="right__image img_section">
					<img class="image" src="@/assets/right_img.jpeg" alt="" />
				</div>
			</div>
			<div class="body__about--right">
				<div class="right__container">
					<h1>Big Love For Our Lovely Kid</h1>
					<p>
						Lorem ipsum dolor sit amet, consectetur adipisicing elit. Quas nisi cumque culpa, nulla
						ducimus placeat perferendis quae
					</p>
					<h5>CONTACT US</h5>
				</div>
			</div>
		</div>
		<div class="body__team section">
			<div class="body__team--title mid-section">
				<p>Our team</p>
				<div class="body__team--cardGroup">
					<b-card tag="article" class="card" v-for="card in teamCards" :key="card.title">
						<b-card-text class="card__content">
							<div class="card--image">
								<img :src="card.profileImage" alt="" />
							</div>
							<div class="card--info">
								<h2>{{ card.name }}</h2>
								<h3>{{ card.role }}</h3>
								<p>
									{{ card.quote }}
								</p>
								<div class="iconsGroup">
									<font-awesome-icon
										v-for="personal in personals"
										:key="personal.icon"
										:icon="['fab', personal.icon]"
										size="xs"
										class="personal_info"
									/>
								</div>
							</div>
						</b-card-text>
					</b-card>
				</div>
			</div>
		</div>
		<div class="body__benefit section">
			<div class="benefit__container">
				<div class="benefit--term" v-for="benefit in benefits" :key="benefit.title">
					<div class="benefit--term--icon">
						<b-iconstack class="stack--icon" font-scale="3">
							<b-icon stacked :icon="benefit.inner_icon" scale="0.5"></b-icon>
							<b-icon stacked :icon="benefit.outter_icon" class="outer-icon"></b-icon>
						</b-iconstack>
					</div>
					<div class="benefit--term--title">
						<p>{{ benefit.title }}</p>
						<h6>{{ benefit.context }}</h6>
					</div>
				</div>
			</div>
		</div>
	</div>
</template>

<script>
export default {
	name: 'app-body',
	data() {
		return {
			proudTitle: 'What We Are Proud Of.',
			proudCards: [
				{
					stat: '20+',
					title: 'Total top services',
					context: 'lorem ipsum dolor sit amet',
				},
				{
					stat: '15+',
					title: 'Countries',
					context: 'lorem ipsum dolor sit amet',
				},
				{
					stat: '98%',
					title: 'Postitive Feedback',
					context: 'lorem ipsum dolor sit amet',
				},
				{
					stat: '2,558',
					title: 'Usual users',
					context: 'lorem ipsum dolor sit amet',
				},
			],
			teamCards: [
				{
					profileImage: require('../assets/icons/user1.png'),
					name: 'Name 1',
					role: 'CEO & Founder',
					quote:
						'lorem ipsum dolor sit amet, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.',
				},
				{
					profileImage: require('../assets/icons/user2.png'),
					name: 'Name 2',
					role: 'Personel',
					quote:
						'lorem ipsum dolor sit amet, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.',
				},
				{
					profileImage: require('../assets/icons/user3.png'),
					name: 'Name 3',
					role: 'Personel',
					quote:
						'lorem ipsum dolor sit amet, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.',
				},
				{
					profileImage: require('../assets/icons/user4.png'),
					name: 'Name 4',
					role: 'Personel',
					quote:
						'lorem ipsum dolor sit amet, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.',
				},
			],
			personals: [
				{
					icon: 'facebook-f',
				},
				{
					icon: 'twitter',
				},
				{
					icon: 'instagram',
				},
				{
					icon: 'youtube',
				},
			],
			benefits: [
				{
					outter_icon: 'circle',
					inner_icon: 'truck',
					title: 'Free Shipping',
					context: 'Free shipping orders from $150',
				},
				{
					outter_icon: 'circle',
					inner_icon: 'gift-fill',
					title: 'Gift/Discount Codes',
					context: 'Many discount codes every day',
				},
				{
					outter_icon: 'circle',
					inner_icon: 'recycle',
					title: 'Money Return',
					context: 'Return it  within  30 days',
				},
			],
		};
	},
};
</script>

<style scoped lang="scss">
@import '../assets/scss/variables.scss';

.body {
	padding: 0 255px;
	width: 100%;
	height: 100%;
	.section {
		margin-bottom: 100px;
	}
	.mid-section {
		text-align: center;
		font-family: Sansita;
		font-size: 54px;
		font-style: normal;
		font-weight: 700;
		line-height: 70px;
		text-transform: capitalize;
	}
	&__title {
		margin-top: 100px;
		text-align: left;
		width: fit-content;
		p {
			font-family: Sansita;
			font-size: 54px;
			font-style: normal;
			font-weight: 700;
			line-height: 70px; /* 129.63% */
			margin-bottom: 10px;
		}
		&--option {
			display: flex;
			align-items: center;
			h6 {
				font-family: Open Sans;
				font-size: 15px;
				font-style: normal;
				line-height: 26px;
			}
			.vertical-line {
				width: 2px;
				height: 50%;
				background-color: $text-color;
				display: flex;
				margin: 0 15px;
			}
		}
	}
	&__cta {
		margin-top: 70px;
		width: 100%;
		display: grid;
		grid-template-columns: 1fr 1fr;
		&--left {
			background: #e5f8fd;
			padding: 100px 70px;
			text-align: left;
			height: fit-content;
			.about {
				border-radius: 5px;
				background: #e6e6ef;
				width: fit-content;
				padding: 7px 15px;
				color: #ec80a0;
			}
			.quote {
				font-family: Sansita;
				font-size: 54px;
				font-style: normal;
				font-weight: 700;
				line-height: 70px;
				margin-bottom: 40px;
			}

			.contact {
				padding: 17px 40px;
				background-color: #ec80a0;
				color: #fff;
				text-align: center;
				width: fit-content;
				border-radius: 10px;
			}
		}
		&--right {
			width: 100%;
			height: 100%;
			display: grid;
			.video {
				align-self: center;
				video {
					width: 100%;
					height: 100%;
				}
			}
		}
	}
	&__proud {
		&--title {
			p {
				font-family: Sansita;
				font-size: 54px;
				font-style: normal;
				font-weight: 700;
				line-height: 70px;
				margin-bottom: 50px;
			}
		}
		&--cardGroup {
			width: 100%;
			height: 100%;
			display: grid;
			grid-template-columns: 1fr 1fr 1fr 1fr;
			column-gap: 30px;
			.card {
				cursor: pointer;
				border-radius: 10px;
				box-shadow: 0px 4px 30px 0px rgba(10, 30, 35, 0.1);
				h2 {
					font-weight: 700;
					line-height: 55px;
					font-family: Sansita;
					font-size: 42px;
					color: $pink-color;
					margin-bottom: 20px;
				}
				h3 {
					text-align: center;
					font-family: Barlow;
					font-size: 24px;
					font-style: normal;
					font-weight: 700;
					line-height: 31px;
				}
			}
		}
	}
	&__about {
		display: grid;
		grid-template-columns: 2fr 1fr;
		gap: 30px;
		width: 100%;

		&--left {
			display: grid;
			grid-template-columns: 1fr 1fr;
			gap: 30px;
			width: 100%;
			height: 100%;

			.img__section {
				align-self: center;
			}
			.left__image {
				width: 100%;
				height: 80%;

				.image {
					width: 100%;
					height: 100%;
					object-fit: fill;
					border-radius: 10px;
				}
			}
			.right__image {
				width: 100%;
				height: 100%;
				.image {
					width: 100%;
					height: 100%;
					object-fit: fill;
					border-radius: 10px;
				}
			}
		}
		&--right {
			width: 100%;
			height: 100%;
			display: flex;
			align-items: center;
			.right__container {
				width: 100%;
				height: 80%;
				background-color: $main-color;
				border-radius: 10px;
				display: flex;
				padding: 0 41px;
				flex-direction: column;
				align-items: center;
				justify-content: center;
				h1 {
					font-family: Sansita;
					font-size: 54px;
					font-style: normal;
					line-height: 70px;
					font-weight: 700;
					margin-bottom: 40px;
				}
				p {
					font-family: Open Sans;
					font-size: 15px;
					font-style: normal;
					font-weight: 400;
					line-height: 26px;
					/*margin-bottom: 40px;*/
				}
				h5 {
					padding: 14px 30px;
					background-color: $pink-color;
					color: $white-color;
					border-radius: 10px;
					width: fit-content;
				}
			}
		}
	}
	&__team {
		width: 100%;
		height: 100%;
		&--title {
			p {
				font-family: Sansita;
				font-style: normal;
				font-weight: 700;
				line-height: 70px;
				margin-bottom: 50px;
			}
		}
		&--cardGroup {
			width: 100%;
			height: 100%;
			display: grid;
			grid-template-columns: 1fr 1fr 1fr 1fr;
			column-gap: 30px;
			.card__content {
				display: flex;
				flex-direction: column;
				height: 100%;
				margin: 0;
				.card--image {
					width: 80%;
					place-self: center;
					margin-bottom: 30px;
					img {
						height: auto;
						width: 100%;
						object-fit: contain;
					}
				}
				.card--info {
					display: flex;
					flex-direction: column;
					h2 {
						font-family: Barlow;
						font-size: 24px;
						font-weight: 700;
						line-height: 31px;
					}
					h3 {
						font-family: Open Sans;
						font-size: 15px;
						font-weight: 400;
						line-height: 26px;
						opacity: 0.5;
					}
					p {
						font-size: 1rem;
						line-height: 1.5rem;
						font-family: Open Sans;
						font-size: 15px;
						font-weight: 400;
						line-height: 26px;
						margin: 0;
					}
					.iconsGroup {
						margin-top: 15px;
						display: flex;
						justify-content: center;
						height: 16px;
						.personal_info {
							height: 100%;
							width: fit-content;
							cursor: pointer;
							margin: 0 5px;
						}
					}
				}
			}
			.card {
				border-radius: 10px;
				box-shadow: 0px 4px 30px 0px rgba(10, 30, 35, 0.1);
			}
		}
	}
	&__benefit {
		width: 100%;
		height: 160px;
		border: 1px solid rgb(200, 200, 200);
		border-radius: 10px;
		.benefit__container {
			display: grid;
			grid-template-columns: 1fr 1fr 1fr;
			width: 100%;
			height: 100%;
			.benefit--term {
				place-self: center;
				display: flex;
				gap: 20px;
				&--icon {
					.stack--icon {
						color: $pink-color;
					}
				}
				&--title {
					text-align: left;
					p {
						font-family: Sansita;
						font-size: 24px;
						font-weight: 700;
						line-height: 31px;
						margin-bottom: 10px;
					}
					h6 {
						font-family: Open Sans;
						font-size: 15px;
						font-weight: 400;
						line-height: 26px;
						margin: 0;
					}
				}
			}
		}
	}
}
@media screen and (max-width: 1700px) {
	.body {
		padding: 0 150px;
		width: 100%;
		height: 100%;
		.section {
			margin-bottom: 100px;
		}
		&__title {
			margin-top: 100px;
			text-align: left;
			width: fit-content;
			p {
				font-family: Sansita;
				font-size: 54px;
				font-style: normal;
				font-weight: 700;
				margin-bottom: 10px;
			}
			&--option {
				display: flex;
				align-items: center;
				h6 {
					font-family: Open Sans;
					font-size: 15px;
					font-style: normal;
					line-height: 26px;
				}
				.vertical-line {
					width: 2px;
					height: 50%;
					background-color: $text-color;
					display: flex;
					margin: 0 15px;
				}
			}
		}
		&__cta {
			margin-top: 70px;
			width: 100%;
			display: grid;
			grid-template-columns: 1fr 1fr;
			&--left {
				padding: 100px 70px;
				text-align: left;
				height: fit-content;
				.about {
					border-radius: 5px;
					background: #e6e6ef;
					width: fit-content;
					padding: 7px 15px;
					color: #ec80a0;
				}
				.quote {
					font-family: Sansita;
					font-size: 54px;
					font-style: normal;
					font-weight: 700;
					line-height: 70px;
					margin-bottom: 40px;
				}
				.contact {
					padding: 17px 40px;
					background-color: #ec80a0;
					text-align: center;
					width: fit-content;
					border-radius: 10px;
				}
			}
			&--right {
				width: 100%;
				height: 100%;
				display: grid;
				.video {
					align-self: center;
					video {
						width: 100%;
						height: 100%;
					}
				}
			}
		}
		&__proud {
			&--title {
				p {
					font-family: Sansita;
					font-size: 54px;
					font-style: normal;
					font-weight: 700;
					line-height: 70px;
					margin-bottom: 50px;
				}
			}
			&--cardGroup {
				width: 100%;
				height: 100%;
				display: grid;
				grid-template-columns: 1fr 1fr 1fr 1fr;
				column-gap: 30px;
				.card {
					cursor: pointer;
					border-radius: 10px;
					box-shadow: 0px 4px 30px 0px rgba(10, 30, 35, 0.1);
					h2 {
						font-weight: 700;
						line-height: 55px;
						font-family: Sansita;
						font-size: 42px;
						color: $pink-color;
						margin-bottom: 20px;
					}
					h3 {
						text-align: center;
						font-family: Barlow;
						font-size: 24px;
						font-style: normal;
						font-weight: 700;
						line-height: 31px;
					}
				}
			}
		}
		&__about {
			display: grid;
			grid-template-columns: 2fr 1fr;
			gap: 30px;
			width: 100%;

			&--left {
				display: grid;
				grid-template-columns: 1fr 1fr;
				gap: 30px;
				width: 100%;
				height: 100%;

				.img__section {
					align-self: center;
				}
				.left__image {
					width: 100%;
					height: 80%;

					.image {
						width: 100%;
						height: 100%;
						object-fit: fill;
						border-radius: 10px;
					}
				}
				.right__image {
					width: 100%;
					height: 100%;
					.image {
						width: 100%;
						height: 100%;
						object-fit: fill;
						border-radius: 10px;
					}
				}
			}
			&--right {
				width: 100%;
				height: 100%;
				display: flex;
				align-items: center;
				.right__container {
					width: 100%;
					height: 80%;
					background-color: $main-color;
					border-radius: 10px;
					display: flex;
					padding: 0 41px;
					flex-direction: column;
					align-items: center;
					justify-content: center;
					h1 {
						font-family: Sansita;
						font-size: 2.5rem;
						font-style: normal;
						line-height: 70px;
						font-weight: 700;
						margin-bottom: 40px;
					}
					p {
						font-family: Open Sans;
						font-size: 15px;
						font-style: normal;
						font-weight: 400;
						line-height: 26px;
					}
					h5 {
						padding: 14px 30px;
						background-color: $pink-color;
						border-radius: 10px;
						width: fit-content;
					}
				}
			}
		}
	}
}
@media screen and (max-width: 1550px) {
	.body {
		width: 100%;
		.section {
			margin-bottom: 100px;
		}
		/* &__title {
			margin-top: 100px;
			text-align: left;
			width: fit-content;
			p {
				font-family: Sansita;
				font-size: 54px;
				font-style: normal;
				font-weight: 700;
				margin-bottom: 10px;
			}
			&--option {
				display: flex;
				align-items: center;
				h6 {
					font-family: Open Sans;
					font-size: 15px;
					font-style: normal;
					line-height: 26px;
				}
				.vertical-line {
					width: 2px;
					height: 50%;
					background-color: $text-color;
					display: flex;
					margin: 0 15px;
				}
			}
		}
		&__cta {
			margin-top: 70px;
			width: 100%;
			background: #e5f8fd;
			display: grid;
			grid-template-columns: 1fr 1fr;
			&--left {
				padding: 100px 70px;
				text-align: left;
				height: fit-content;
				.about {
					border-radius: 5px;
					background: #e6e6ef;
					width: fit-content;
					padding: 7px 15px;
					color: #ec80a0;
				}
				.quote {
					font-family: Sansita;
					font-size: 54px;
					font-style: normal;
					font-weight: 700;
					line-height: 70px;
					margin-bottom: 40px;
				}
				.contact {
					padding: 17px 40px;
					background-color: #ec80a0;
					text-align: center;
					width: fit-content;
					border-radius: 10px;
				}
			}
			&--right {
				width: 100%;
				height: 100%;
				display: grid;
				.video {
					align-self: center;
					video {
						width: 100%;
						height: 100%;
					}
				}
			}
		}
		&__proud {
			&--title {
				p {
					font-family: Sansita;
					font-size: 54px;
					font-style: normal;
					font-weight: 700;
					line-height: 70px;
					margin-bottom: 50px;
				}
			}
			&--cardGroup {
				width: 100%;
				height: 100%;
				display: grid;
				grid-template-columns: 1fr 1fr 1fr 1fr;
				column-gap: 30px;
				.card {
					cursor: pointer;
					border-radius: 10px;
					box-shadow: 0px 4px 30px 0px rgba(10, 30, 35, 0.1);
					h2 {
						font-weight: 700;
						line-height: 55px;
						font-family: Sansita;
						font-size: 42px;
						color: $pink-color;
						margin-bottom: 20px;
					}
					h3 {
						text-align: center;
						font-family: Barlow;
						font-size: 24px;
						font-style: normal;
						font-weight: 700;
						line-height: 31px;
					}
				}
			}
		} */
		&__about {
			display: grid;
			grid-template-columns: 2fr 1fr;
			gap: 30px;
			width: 100%;

			/*	&--left {
				display: grid;
				grid-template-columns: 1fr 1fr;
				gap: 30px;
				width: 100%;
				height: 100%;

				.img__section {
					align-self: center;
				}
				.left__image {
					width: 100%;
					height: 80%;

					.image {
						width: 100%;
						height: 100%;
						object-fit: fill;
						border-radius: 10px;
					}
				}
				.right__image {
					width: 100%;
					height: 100%;
					.image {
						width: 100%;
						height: 100%;
						object-fit: fill;
						border-radius: 10px;
					}
				}
			} */
			&--right {
				width: 100%;
				height: 100%;
				display: flex;
				align-items: center;
				.right__container {
					width: 100%;
					height: 80%;
					background-color: $main-color;
					border-radius: 10px;
					display: flex;
					padding: 0 20px;
					flex-direction: column;
					align-items: center;
					justify-content: center;
					h1 {
						font-family: Sansita;
						font-size: 2rem;
						font-style: normal;
						line-height: 30px;
						font-weight: 700;
						margin-bottom: 20px;
					}
					p {
						font-family: Open Sans;
						font-size: 15px;
						font-style: normal;
						font-weight: 400;
						line-height: 26px;
						font-size: 1rem;
					}
					h5 {
						font-size: 1.3rem;
						padding: 5px 10px;
						background-color: $pink-color;
						border-radius: 10px;
						width: fit-content;
					}
				}
			}
		}
	}
}
@media screen and (max-width: 480px) {
	.body {
		padding: 0;
		&__title {
			width: 100%;
			text-align: center;
			margin-top: 60px;
			&--option {
				justify-content: center;
			}
		}
		&__cta {
			display: flex;
			margin-top: 25px;
			grid-template-columns: 1fr;
			flex-direction: column-reverse;
			&--left {
				padding: 60px;
				display: flex;
				flex-direction: column;
				align-items: center;
				.about {
					font-size: 15px;
				}
				.quote {
					font-family: Sansita;
					font-size: 30px;
					line-height: 40px;
					margin-bottom: 30px;
				}
				.contact {
					padding: 13px 30px;
					font-size: 17px;
				}
			}
		}
		&__proud {
			&--title {
				p {
					font-family: Sansita;
					font-size: 36px;
					font-weight: 700;
					line-height: 47px;
				}
			}
			&--cardGroup {
				grid-template-columns: 1fr;
				padding: 0 20px;
				gap: 20px;
			}
		}
		&__about {
			grid-template-columns: 1fr;
			&--left {
				gap: 0;
				.left__image {
					height: 100%;
					padding: 10px 20px;
				}
			}
			&--right {
				padding: 0 20px;
				height: 100%;
				.right__container {
					height: 100%;
					padding: 20px;
					h1 {
						padding: 0 60px;
					}
					h5 {
						color: $white-color;
						padding: 13px 30px;
					}
				}
			}
		}
		&__team {
			&--title {
				p {
					font-family: Sansita;
					font-size: 36px;
					font-weight: 700;
					line-height: 47px;
				}
			}
			&--cardGroup {
				grid-template-columns: 1fr;
				padding: 0 20px;
				gap: 20px;
			}
		}
		&__benefit {
			display: none;
		}
	}
}
</style>
