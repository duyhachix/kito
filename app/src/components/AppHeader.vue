<template>
	<header class="header">
		<div class="header__credit">
			<div class="header__credit--left">KITO - Every day low price</div>
			<div class="header__credit--center">{{ centerContext }}</div>
			<div class="header__credit--right">
				<div class="dropdownGroup">
					<el-dropdown>
						<span class="el-dropdown-link">
							USA<i class="el-icon-arrow-down el-icon--right"></i>
						</span>
						<el-dropdown-menu slot="dropdown">
							<el-dropdown-item v-for="locale in locales" :key="locale"
								>{{ locale }}
							</el-dropdown-item>
						</el-dropdown-menu>
					</el-dropdown>
					<div class="vertical-line"></div>
					<el-dropdown>
						<span class="el-dropdown-link">
							USD<i class="el-icon-arrow-down el-icon--right"></i>
						</span>
						<el-dropdown-menu slot="dropdown">
							<el-dropdown-item v-for="current in currents" :key="current">{{
								current
							}}</el-dropdown-item>
						</el-dropdown-menu>
					</el-dropdown>
				</div>
			</div>
		</div>
		<div class="header__nav">
			<div class="navbar">
				<b-nav>
					<b-nav-item>Home</b-nav-item>
					<b-nav-item>Shop</b-nav-item>
					<b-nav-item>
						<el-dropdown>
							<span>Page<i class="el-icon-arrow-down el-icon--right"></i></span>
							<el-dropdown-menu slot="dropdown">
								<el-dropdown-item v-for="page in pages" :key="page">{{ page }}</el-dropdown-item>
							</el-dropdown-menu>
						</el-dropdown>
					</b-nav-item>
					<b-nav-item>Contact</b-nav-item>
				</b-nav>
			</div>
			<div class="title">{{ title }}</div>
			<div class="cart">
				<div class="cart__group">
					<div class="icon" style="position: relative; display: inline-block">
						<b-icon font-scale="1.5" icon="search"></b-icon>
					</div>
					<div class="icon" style="position: relative; display: inline-block">
						<b-icon font-scale="1.5" icon="cart4"></b-icon>
						<b-badge variant="dark" class="badge-bottom-right">0</b-badge>
					</div>
					<div class="icon" style="position: relative; display: inline-block">
						<b-icon font-scale="1.5" icon="heart"></b-icon>
						<b-badge variant="dark" class="badge-bottom-right">0</b-badge>
					</div>
				</div>
			</div>
		</div>
	</header>
</template>

<script>
export default {
	nam: 'app-header',
	data() {
		return {
			title: 'KITO',
			leftContext: 'KITO - Every day low price',
			centerContext: `Free Delivery on orders over £120. Don't miss discount.`,
			locales: ['en-US', 'vi-VN', 'ja-JP'],
			currents: ['USD', 'VND', 'JPY'],
			pages: ['Toy', 'Furniture', 'Fashion'],
		};
	},
};
</script>

<style lang="scss" scoped>
@import '../assets/scss/variables.scss';
.header {
	width: 100%;
	height: 150px;
	color: red;
	&__credit {
		font-family: Open Sans;
		z-index: 2;
		padding: 0 255px;
		display: flex;
		justify-content: space-between;
		height: 40px;
		font-weight: 400;
		background-color: $main-color;
		font-size: 15px;
		line-height: 26px; /* 173.333% */
		&--left {
			color: $text-color;
			z-index: 2;
			align-self: center;
		}
		&--center {
			z-index: 2;
			color: #c81b10;
			align-self: center;
		}
		&--right {
			.dropdownGroup {
				height: 100%;
				display: flex;
				align-items: center;
				.el-dropdown-link {
					color: $text-color;
				}
				.vertical-line {
					display: flex;
					margin: 0 15px;
					width: 1px;
					opacity: 0.1;
					background-color: $text-color;
					height: 50%;
				}
			}
		}
	}
	&__nav {
		padding: 0 255px;
		height: calc(100% - 40px);
		background-color: $white-color;
		box-shadow: 0px 2px 20px 0px rgba(26, 17, 20, 0.1);
		display: grid;
		grid-template-columns: 1fr 1fr 1fr;
		justify-content: space-between;
		.nav-item {
			span {
				color: $text-color;
			}
		}
		.navbar {
			padding: 0;
			font-size: 15px;
			font-weight: 700;
			.nav {
				column-gap: 40px;
			}
			.nav-link {
				padding: 0;
				color: #000;
			}
		}
		.title {
			color: $text-color;
			align-self: center;
			justify-self: center;
			text-align: center;
			font-family: Sansita;
			font-size: 54px;
			font-weight: 800;
			line-height: 70px; /* 129.63% */
		}
		.cart {
			color: $text-color;
			align-self: center;
			justify-self: end;
			&__group {
				display: grid;
				grid-template-columns: repeat(3, 1fr);
				align-items: center;
				gap: 30px;
				.icon {
					cursor: pointer;
				}
				.badge-bottom-right {
					position: absolute;
					bottom: -5px;
					right: -5px;
				}
			}
		}
	}
}
</style>
