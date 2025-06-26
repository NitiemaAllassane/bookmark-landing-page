<script>
    import closeIcon from '../../assets/images/icon-close.svg';
    let { onButtonClick } = $props();
</script>

<button 
    aria-label="close menu"
    onclick={onButtonClick}
>
    <img src={closeIcon} alt="" aria-hidden="true">
</button>