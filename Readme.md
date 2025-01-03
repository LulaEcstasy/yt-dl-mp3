Download FFMPEG essentials
extract files to folder ffmpeg:

    ffmpeg \ 
    > ffmpeg.exe
    > ffplay.exe
    > ffprobe.exe

on list.txt place you links to download

RUN.bat 
run the all proces.

    @echo off
    powershell -ExecutionPolicy Bypass -File ".\scr\skrypt1.ps1"
    pause  

skrypt1.ps1 
easy transition from bat to ps1:

         get-content ".\scr\skrypt2.txt" | Invoke-Expression

skrypt2.txt 
the whole command to run the yt-dl.exe options so that the links from list.txt are downloaded one by one and converted to mp3:

    ./scr/yt-dlp -x --audio-format mp3 --audio-quality 0 --ffmpeg-location ".\ffmpeg\" -a ".\list.txt" -o ".\Downloads\%(title)s-%(id)s.%(ext)s"

