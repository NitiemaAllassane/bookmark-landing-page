<script>
    import menuHamburger from '../../assets/images/icon-hamburger.svg';
    let { onButtonClick } = $props();
</script>

<button 
    class="md:hidden" 
    aria-label="Open menu"
    onclick={onButtonClick}
>
    <img src={menuHamburger} alt="" aria-hidden="true">
</button>