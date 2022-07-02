
[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/shubham8550/Google-Drive-Torrent-Downlaoder/blob/main/Google_Drive_Torrent_Downlaoder.ipynb)


> Using This python .ipynb Script on Google Colab you can directly
> Transfer/download Torrent in your Google Drive Account

---

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/shubham8550/Google-Drive-Torrent-Downlaoder/blob/main/Google_Drive_Torrent_Downlaoder.ipynb)

**How To?**
Open This Script in google colab change magnet link in 4th cell And Run Each Cell One By One As mentioned Below.



**Step 1** : install libtorrent Package


    !apt-get install python3-libtorrent

**Step 2**  : Import libtorrent



    import libtorrent as lt

**Step 3**  : Mount your Google Drive


    from google.colab import drive
    
    drive.mount('/content/gdrive2')

**Step 4**  : Replace your Magnet Link And Run Cell ,And thats It. Have a Fun !!


    import libtorrent as lt
    import time
    
    ses = lt.session()
    params = { 'save_path': '/content/gdrive2/My Drive'}
    link = "magnet:?xt=urn:btih:d72af2a6f1b29537399db84a5093287d9a3fecee&dn=Unity-2020.1.16f1"
    handle = lt.add_magnet_uri(ses, link, params)
    
    print('downloading metadata...')
    while (not handle.has_metadata()): time.sleep(1)
    print('got metadata, starting torrent download...')
    while (handle.status().state != lt.torrent_status.seeding):
        print('%d  %% done' % (handle.status().progress*100))
        time.sleep(1)

----------

> Repository
> :[https://github.com/shubham8550/Google-Drive-Torrent-Downlaoder](https://github.com/shubham8550/Google-Drive-Torrent-Downlaoder)
> 
> Star My Repository and follow me on Github.
<img alt="shubham8550/stars-github" src="https://stars-github.herokuapp.com/shubham8550/Google-Drive-Torrent-Downlaoder">
