# Monitoring
## Audio monitoring
Audio monitoring starts immediately when a correct audio source is active. The decoded audio stream is rendered on the default device soundcard. This stream is a binaural audio stream meant to be listened with headphones.

### Renderer ambisonics order
As different 360 video player handles different type of audio formats, the audio renderer embedded in Cinematic VR can be configured  to decode audio only at a certain ambisonics resolution.
In future version, we will provide more ambisonics rendering option to be able to monitor with an audio rendering as close as possible from the destination renderer.

### HRTF configuration
HRTFs (or Head Related Transfer Function) depict how your ears hear the world. These are different for each individuals. Cinematic VR let you choose between several HRTFs incoming from the Listen database.

The possibility to import your own HRTFs will be provided shortly. To do so, your HRTF will have to be a SOFA file.

## VR Monitoring
Being able to put a VR headset while mixing is maybe the most important good practive to have while mixing for VR. Cinematic VR has an integrated tool to launch a 360 video player directly.
The video player is a separated app that communicates with Cinematic VR through OSC (for headtracking information) and Midi Time Code (for synchronization).

To display the video correctly, check that your project was saved before launching the video player.

The video player can handle Monoscopic and Stereoscopic contents. Before hitting Launch, you can choose whether yout content is Mono, Stereo Top/Bottom or Side by side.

The video player uses OpenVR to communicate with the HMD. This protocol is natively supported by HTC Vive headsets, but can be used easily with Oculus Rift by installing SteamVR. These are the only officially supported headsets even if other headsets with OpenVR support may be compatible.