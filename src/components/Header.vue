<template>
	<div class="navigation">
		<div class="row">
			<div class="col-md-3">
				<div class="logo">
					<!-- <img alt="Vue logo" src="../assets/logo.png" width="50" height="50"> -->
				</div>
			</div>

			<div class="col-md-6">
				<ul class='menu'>
					<li v-for="item in menuHeaderItems" v-bind:key="item.id">
						<span class="menu-element">{{item.name}}</span>
						<b-icon style="margin-left:5px;" icon="chevron-down"></b-icon>
					</li>
				</ul>
				
			</div>
			<div class="col-md-3">
				<div class="user-info">
					<img class='avatar' alt="avatar-user" src="../assets/avatar.jpg">
					<label for="" class='user-name'>Arek Ścibior</label>
					<b-icon class='gear-icon' icon="gear-fill"></b-icon>
					<b-button variant="primary" class="mb-2 logout-button">
						<b-icon icon="power" aria-hidden="true"></b-icon> Logout
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
	.navigation {
		background-color: #C60321;
		opacity: 0.85;
		height: 80px;
	}
	.menu {
		display: inline-flex;
		margin: 0;
		line-height: 80px;
	}
	.menu li {
		margin: 0px 60px 0 0;
		text-decoration: none;
		list-style-type: none;
		cursor: pointer;
		color: #fff;
		font-size: 16px;

	}
	.menu-element:hover {
		border-bottom: 2px solid #fff;
	}
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
		fill: #fff; 
		cursor: pointer;
	}

	.logout-button {
		background-color: #fff !important;
		border: none !important;
		color: #000 !important;
		font-weight: bold;
		margin-left: 25px;
	}
</style>
