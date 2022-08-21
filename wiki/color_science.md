#### color science  
* cinemaDNG - open source format, not a set way for camera to put in metadata .  

method:  
* transform CDNG into linear space and convert to ARRI color and LogC.  
* RAW is just RGB values coming off the senson with no "color science" applied.  
* linear space is mathematically similar to RAW in that its just manipulating RGB values to take data and fold it to a curve that looks good in a set color space.  
* CinemaDNG RAW and setup in Resolv with RAW tab to be linear in output with P3D60 (wide color gamut) and Linear.  

* ARRI LogC -  C is gor Cineon.  uses scene-based encoding.  signal level increased by a fixed amount with each increase of exposure, measured in stops.

* if you use Log it is no longer RAW.  RAW files have linear signal by definition.  
* RAW image is stored without any processing done by the camera.  
* CinemaDNG has smaller file size that RAW.  


Long GOP and All-Intra
* GOP - smaller files, lower quality
* All-I - larger files, getter quality

Long Group of Pictures:  

