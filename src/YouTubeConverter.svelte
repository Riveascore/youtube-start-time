<script context="module">
	export const getSeconds = (timeString) => {
		if (timeString === '') {
			return '';
		}
		
    let [hours, minutes, seconds] = timeString.split(':')

		if(typeof seconds === 'undefined') {
			seconds = parseInt(minutes);
			minutes = parseInt(hours);
			hours = 0;
		}

    return hours * 3600 + minutes * 60 + seconds;
	}

	export const youtubeTimeSuffix = (seconds) => {
		return `&t=${getSeconds(seconds)}s`;
	}

	export const youtubeLinkWithTime = (link, timeString) => {
		if (link === '' || timeString === '') {
			return '';
		}
		
		return `${link}${youtubeTimeSuffix(timeString)}`;
	}
</script>