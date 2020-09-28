<template>
	<div class="navigation">
		<div class="row">
			<div class="col-md-3">
				<div class="logo">
					<span class='logo-name'>BANCO</span>
				</div>
			</div>

			<div class="col-md-6">
				<ul class='menu'>
					<li v-for="item in menuHeaderItems" v-bind:key="item.id">
						<span class="menu-element">{{item.name}}</span>
						<span v-if="item.hasSub"><b-icon class='icon-down' icon="chevron-down"></b-icon></span>
					</li>
				</ul>
				
			</div>
			<div class="col-md-3">
				<div class="user-info">
					<img class='avatar' alt="avatar-user" src="../assets/avatar.jpg">
					<label for="" class='user-name'>Arek Ścibior</label>
					<b-icon class='gear-icon' icon="gear-fill"></b-icon>
					<b-button variant="primary" class="mb-2 logout-button focus:outline-none">
						<b-icon icon="power" style="font-weight: bold;" aria-hidden="true"></b-icon> Logout
					</b-button>
				</div>
				
				<div class="settings">

				</div>
			</div>	
		</div>
	</div>
</template>

<script>
export default {
	name: 'Header',
	props: {
		msg: String
	},
	data() {
		return { 
			menuHeaderItems: [
				{id:'0', name: 'Płatności', hasSub: true, sub: ['Przelew', 'Lista zdefiniowanych kontaktów', 'Zlecenia stałe']},
				{id:'1', name: 'Historia', hasSub: false},
				{id:'2', name: 'Karty', hasSub: true, sub: ['Moje karty']},
				{id:'3', name: 'Lokaty', hasSub: false},
				{id:'4', name: 'Finanse', hasSub: false},
				{id:'5', name: 'Oferty', hasSub: false},
				{id:'6', name: 'Kontakt', hasSub: false},
			]
		}
	} 
}
</script>

<style>
	@import url('https://fonts.googleapis.com/css2?family=Monoton&display=swap');

	.navigation {
		background-color: #C60321;
		opacity: 0.85;
		height: 80px;
	}

	/* left side	 */
	.logo {
		line-height: 80px;
		text-align: left;
		margin-left: 35px;
	}
	.logo .logo-name {
		font-family: 'Monoton', cursive;
		color: #fff;
		font-size: 40px;
	}
	.icon-down {
		font-size: 19px;
		font-weight: bold;
		margin-left: 5px;
	}

	/* center side */
	.menu {
		display: inline-flex;
		margin: 0;
		line-height: 80px;
	}
	.menu li {
		margin: 0px 50px 0 0;
		text-decoration: none;
		list-style-type: none;
		cursor: pointer;
		color: #fff;
		font-size: 16px;

	}
	.menu-element:hover {
		border-bottom: 2px solid #fff;
	}

	/* right side */
	.user-info {line-height: 80px;}
	.avatar {
		width: 40px;
		height: 40px;
		border-radius: 50%;
		cursor: pointer;
	}
	.user-name {
		color: #fff;
		padding-left: 10px;
	}
	.gear-icon {
		margin-left:5px;
		margin-top: -3px;
		fill: #fff; 
		cursor: pointer;
	}
	.logout-button {
		background-color: #fff !important;
		border: none !important;
		color: #000 !important;
		font-size: 15px !important;
		font-weight: bold !important;
		margin-left: 25px !important;
		padding: 7px !important;
		outline: none !important;
	}
	.logout-button:focus {
		box-shadow: 0 0 0 0.2rem rgb(255 38 38 / 0%) !important;
	}
	.logout-button:hover {
		background-color: rgba(228, 217, 217, 0.877) !important;
	}
</style>
