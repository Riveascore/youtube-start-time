<script>		
	import {
		getSeconds, 
		youtubeTimeSuffix, 
		youtubeLinkWithTime 
	} from './YouTubeConverter.svelte';
	
	import Toast from './Toast.svelte'
	
	import { 
		copyYouTubeLink 
	} from './CopyRevealCode.svelte';
	
	let youtubeLink = '';
	let timeMarker = '';
	
	let inputSizes = 45;
</script>




<h1 class="red">
	<i class="fab fa-youtube"></i> YouTube Start Time
</h1>

<input bind:value={youtubeLink} placeholder="Paste YouTube link" size={inputSizes}>
<br/>
<input bind:value={timeMarker} placeholder="Enter time value (i.e. 1:57)" size={inputSizes}>

<Toast />

<h3>
	<i class="far fa-clock"></i> New Link with Time Marker:
</h3>
<p style="min-height: 23px;">
	{youtubeLinkWithTime(youtubeLink, timeMarker) || ''}
</p>

	<button on:click={copyYouTubeLink}>
		<i class="far fa-copy"></i> Copy Link with Time Marker
	</button>

<input type="hidden" value={youtubeLinkWithTime(youtubeLink, timeMarker)} id="youtube-link-with-time">








<style>
	.red {
		color: #ff4757;
	}
/* 	.purple {
		color: #3742fa;
	}
	.gray {
		color: #2f3542;
	}
	.green {
		color: #2ed573;
	}
	.blue {
		color: #1e90ff;
	} */
</style>




<link rel="stylesheet" href="https://pro.fontawesome.com/releases/v5.10.0/css/all.css" integrity="sha384-AYmEC3Yw5cVb3ZcuHtOA93w35dYTsvhLPVnYs9eStHfGJvOvKxVfELGroGkvsg+p" crossorigin="anonymous"/>