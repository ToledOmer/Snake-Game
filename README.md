sound -

       1. tried to use the windows.h library but **failed** because im using Ubuntu.
       2. installing SDL2 library.
       3. many attempts in order to adjust the CMakeLists.txt file to the SDL2 library.
       4. Creating AudioPlayer.h .
       5. Tried using threads to check if the background music finished (and then replay it) -- **failed** due to technical problems.
       6. tried to work with clock() -- hard to estimate when the song is over -- **failed**.
       7. Creating a field ot timer_t in order to save the starting of the song and check in the Dispaly.cpp of the song is over due
          due to time difference.
       8. background song is working.
       9. new error - "ALSA lib pcm.c:8432:(snd_pcm_recover) underrun occurred".
       10. solved error by closing the audioDeviceID and clean the wav buffer.
       11. the music works but we still get the weird red error, probably because of drivers problems


camera and screens -

       1.working with camera_translation , camera_eye , camera_up
       
        a.camera_translation is the location of the eye , which is the center of snake's head (given by multiplying the whole
         translation matrix of the cylinder from the bottom to the head) + 0.83(rotation vector of the head).
         
        b.camera_eye - camera_eye is the direction which the eye are looking to  (vector),
          after some thinking the vector we are looking for is the same vector from assignment 4, the same "a ,b ,c " of the face A0
          which we calculated by getting the rotation matrix of the snake head(by multiplying the rotation matrices of
          the snake from the bottom to the top).

        c. camera_up - similarly to "camera_eye" , we are looking for the "a ,b ,c " of the face A1 (as described in assignment 4),
            we get this vector in a similar way we found A0,
            
 some problem we encountered:
 
         i. resizing the windows  - we accidentally used , 0 and 1 , instead of using unsigned int "right view" & "left view"
         
         ii. A few things need an adjustment because splitting the screen the same as libigl 108 tutorial (most of the function related to the
            core is in the viewer as opposed to our project)
            
            
         iii. after collusion we set the mesh invisible and between levels we load new meshes, we need to make sure they visible in the
            right viewport because of the differences between our appendMesh() and the libigl 108 appendMesh()


Video Playing -

              1.we wanted to play videos
                a. at the begging
                b. between stages
                c. credit video in the end
              2.Downloaded openCV library
              3.we dealt many problem while installing it
              4.eventually the library is installed and downloaded successfully
              5.tried to use online tutorials
              6. two errors "[ WARN:0] global /opt/opencv/modules/videoio/src/cap_gstreamer.cpp (713) open OpenCV | GStreamer warning: Error opening bin: unexpected reference "VideoPath" - ignoring
                             [ WARN:0] global /opt/opencv/modules/videoio/src/cap_gstreamer.cpp (480) isPipelinePlaying OpenCV | GStreamer warning: GStreamer: pipeline have not been created"
              7. couldn't solve this problem, reason: using ubuntu might cause graphic engine problem


