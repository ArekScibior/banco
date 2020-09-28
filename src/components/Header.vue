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
						<span class="menuElement">{{item.name}}</span>
						<b-icon style="margin-left:5px;" icon="chevron-down"></b-icon>
					</li>
				</ul>
				
			</div>
			<div class="col-md-3">
				<div class="userInfo">
					<img class='avatar' alt="avatarUser" src="../assets/avatar.jpg">
					<label for="" class='userName'>Arek Ścibior</label>
					<b-icon style="margin-left:5px; fill: #fff; cursor: pointer;" icon="gear-fill"></b-icon>
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
				{id:'1', name: 'Karty', hasSub: true, sub: ['Moje karty']},
				{id:'2', name: 'Kontakt', hasSub: false}
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
		font-size: 20px;

	}
	/* .menuElement {
		
	} */
	.menuElement:hover {
		border-bottom: 2px solid #fff;
	}
	.userInfo {line-height: 80px;}
	.avatar {
		width: 40px;
		height: 40px;
		border-radius: 50%;
		cursor: pointer;
	}
	.userName {
		color: #fff;
		font-weight: bold;
		padding-left: 10px;
	}
</style>
