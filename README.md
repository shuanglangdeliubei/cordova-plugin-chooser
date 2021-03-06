# Chooser

## Overview

File chooser plugin for Cordova.

Install with Cordova CLI:

	$ cordova plugin add cordova-plugin-chooser

Supported Platforms:

* Android

* iOS

## API

	/**
	 * Displays native prompt for user to select a file.
	 *
	 * @param accept Optional MIME type filter (e.g. 'image/gif,video/*').
	 *
	 * @returns Promise containing selected file's raw binary data,
	 * base64-encoded data: URI, MIME type, display name, and original URI.
	 *
	 * If user cancels, promise will be resolved as undefined.
	 * If error occurs, promise will be rejected.
	 */
	chooser.getFile(accept?: string) : Promise<undefined|{
		data: Uint8Array;
		dataURI: string;
		mediaType: string;
		name: string;
		uri: string;
	}>

## Example Usage

	(async () => {
		const file = await chooser.getFile();
		console.log(file ? file.name : 'canceled');
	})();
