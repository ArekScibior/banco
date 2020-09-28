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
					<li class='item' v-for="item in menuHeaderItems" v-bind:key="item.id" @mouseover="onOver(item)" @mouseleave="onLeave(item)">
						<span class="menu-element">{{item.name}}</span>
						<span v-if="item.hasSub"><b-icon class='icon-down' icon="chevron-down"></b-icon></span>
						<ul v-show="item.showSubs" class="sub-items">
							<li class='sub-item' v-for="subItem in item.sub" v-bind:key="subItem.id">
								{{subItem}}
							</li>
						</ul>
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
				{id:'0', name: 'Płatności', hasSub: true, showSubs: false, sub: ['Przelew', 'Lista zdefiniowanych kontaktów', 'Zlecenia stałe']},
				{id:'1', name: 'Historia', hasSub: false},
				{id:'2', name: 'Karty', hasSub: true, showSubs: false, sub: ['Moje karty']},
				{id:'3', name: 'Lokaty', hasSub: false},
				{id:'4', name: 'Finanse', hasSub: false},
				{id:'5', name: 'Oferty', hasSub: false},
				{id:'6', name: 'Kontakt', hasSub: false},
			]
		}
	},
	methods: {
		onOver(item) {
			item.showSubs = true;
		},

		onLeave(item) {
			item.showSubs = false;
		}
	}
}
</script>

<style>
	@import url('https://fonts.googleapis.com/css2?family=Monoton&display=swap');

	ul, menu, dir {
		display: block;
		list-style-type: none;
		-webkit-margin-before: 1em;
		-webkit-margin-after: 1em;
		-webkit-margin-start: 0px;
		-webkit-margin-end: 0px;
		-webkit-padding-start: 40px;
	}

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
	.menu .item {
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

	.sub-items {
		position: absolute;
		background-color: #c60320de;
		text-align: left;
		margin-top: -1px;
		list-style: none;
		padding: 0;
		width: 320px;
	}
	.sub-items .sub-item {
		color: #fff !important;
		text-decoration: none;
		list-style-type: none;
		cursor: pointer;
		color: #fff;
		font-size: 16px;
		padding-left: 10px;
		padding-right: 10px;
		height: 47px;
		line-height: 47px;
	}

	.sub-items .sub-item:hover {
		background-color: #E01E5A;
	}

	/* right side */
	.user-info {line-height: 80px;}
	.avatar {
		width: 40px;
		height: 40px;
		border-radius: 50%;
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
