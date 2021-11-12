<script context="module">
	
	import {notifications} from './notifications.js'

	
	import { copy } from './utils.js';

	export const copyYouTubeLink = () => {
		let youtubeLinkWithTime = document.getElementById(
			'youtube-link-with-time'
		)
		
		let linkWithTimeVal = youtubeLinkWithTime.value;
		
		if(linkWithTimeVal === '') {
			notifications.danger('Fill in required values', 2000);
			return false;
		}
		
		copy(youtubeLinkWithTime.value);
		notifications.success('Copied to Clipboard', 2000);
	}

</script>