<script>
	import LoginButtons from '@archetypes/Account/LoginButtons.svelte';
	import Centered from '@layouts/Centered.svelte'
	import GantreeLogo from '@assets/GantreeLogo.svelte'
	import AccountMenu from '@archetypes/Account/Menu.svelte'
</script>

<style lang="scss">

	:global(.layout.-centered.home) {
		:global(.children) > :global(.gantree-logo){
			font-size: 4.7em;
		}

		:global(*[slot="header"]){
			justify-content: flex-start !important;
			:global(.account-menu){
				font-size: 0.9em;
				opacity: 0.7;
				transition: opacity 0.15s;

				&:hover{
					opacity: 0.9;
				}
			}
		}

		:global(*[slot="footer"][class*='mdc-typography'] > a){
			color: var(--color-light-grey);
		}
	}

	.gantree-logo{
		margin: 0;
		line-height: 1em;
		font-family: 'Monda', sans-serif;
		text-transform: uppercase;
		font-size: 4.7em;
		color: var(--color-light-purple);
		text-shadow: -2px 2px 0 var(--color-purple);
	}



	h2{
		margin: 0.3em auto 0;
		line-height: 1.1em;
		font-weight: 100;
		max-width: 23rem;
		color: var(--color-light-grey);
	}

	p.-content{
		margin: 4em auto;
		line-height: 1.3em;
		font-weight: 100;
		position: relative;
		color: var(--color-light-grey);

		&:before,
		&:after{
			content: '';
			position: absolute;
			left: 50%;
			width: 50%;
			transform: translateX(-50%);
			border-bottom: 1px solid rgba(255,255,255,0.2)
		}

		&:before{ top: -1.5em }
		&:after{ bottom: -1.5em }
	}

	:global(.user-login-buttons){
		margin-top: 3rem;
	}

	.-credit{
		opacity: 0.8;
	}
</style>

<Centered class={'home'}>
	<span slot='header'>
		<AccountMenu/>
	</span>

	<GantreeLogo/>
	<h2 class="mdc-typography--headline6">A full service node infrastructure toolkit for Substrate-based chains</h2>
	<p class="mdc-typography--body1 -content">
		Deploying and maintaining  blockchains is difficult. We firmly believe that you shouldn't need to be a DevOps professional in order to develop blockchains Gantree can lighten the load on developers, allowing you to focus on building while we do the heavy lifting of managing your infrastructure.
	</p>
	<LoginButtons
		providers={['Google']}
		email={{
			signin: 'LOG IN WITH EMAIL',
			signup: 'CREATE ACCOUNT'
		}}
	/>

	<span slot='footer' class="mdc-typography--body2 -credit">
		Powered By&nbsp;<a href="https://flexdapps.com/" target='_blank' rel="noopener noreferrer">FLEXDAPPS</a>
		&nbsp;&nbsp;|&nbsp;&nbsp;
		<a href="https://www.notion.so/flexdapps/Get-In-Touch-a4e8c3461eed4cbe835b3e2f98ea0c69" target='_blank' rel="noopener noreferrer">Get in touch</a>
	</span>
</Centered>