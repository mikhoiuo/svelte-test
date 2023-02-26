<script>
	export let text;
</script>
<button on:click>{text}</button>

<style>
	button {
    background-color: #F9F3F2;
    font-family: Karla, arial, helvetica;
    font-size: 11px;
    color: #6F6A68;
    cursor: url('http://static.tumblr.com/vmteopo/yYInjhg6e/small_black_cursor.png'), default;
	}

	button:hover {
    color: #EA977D;
    background-color: #E7DCD9;
    cursor: url('https://68.media.tumblr.com/tumblr_lyovxfnDb71qfoi4t.png'), default;
}

	button:focus {
		background: #94a3b8;
		color: #f1f5f9;
	}
</style>