**Transcode Status:** This script monitors the transcoding progress of the uploaded video, displaying a progress bar in the command line interface until transcoding is complete or encounters an error.

**Story:** 
As a developer, I want to upload videos programmatically to Vimeo, verify successful upload, and monitor the transcoding process to ensure that videos are ready for viewing.

**Criteria:**
Upon receiving the request, the Vimeo API should create a video on the Vimeo Servers and provide a response containing an upload link.

After patching the upload link with the video file, I should receive partial upload confirmations from the Vimeo Servers to track the progress.

Once the upload is complete, I should be able to verify the upload by sending a HEAD request to the Vimeo API.

The Vimeo API should confirm the upload and provide the necessary data for further processing.

I should periodically check the transcoding status of the video by sending GET requests to the Vimeo API - how often entirely up to you, am going for 10” in this prototype, let’s call it 'n' in our manifest.

If the transcoding is in progress, I should receive periodic updates on the status until it's complete.

Upon completion of transcoding, the Vimeo API should provide a response indicating the completion of transcoding.

In case of an upload failure, I should receive notifications to handle the failure appropriately.

**Other:** Vimeo has a webhooks API, CAPABILITY_WEBHOOKS. A video’s conversion/transcode status is also returned under the “status” field in the “transcode” object of the video response. This field will return the value “complete”, “error”, or “in_progress.”
You could periodically make GET requests to the API to get the video's transcode status.

**Logic Flow:** 

![image](https://github.com/josev2046/Transcode-status/assets/15835851/878977f5-f984-442f-8b92-ca03255ad230)

**Rapid Prototype:**

https://github.com/josev2046/Transcode-status/assets/15835851/df184548-8ddd-4d72-8d69-8d7dda8a31f3



[![DOI](https://zenodo.org/badge/808330567.svg)](https://doi.org/10.5281/zenodo.15034998)


