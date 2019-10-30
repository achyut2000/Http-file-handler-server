# Http-file-handler-server

## File Handling using the extra options feature of HTTP Protocol(MIME)

The reason for this project is when you want to share files from your phone to pc/laptop or vice versa. What You do???
  - By Using the cable??
  - By some sharing apps??
  - By gmail??
 For one to one these methods works well. But for one to many what you gonna do?????
 
 **Here it is..................**
 
  This was the reason for my project. In this project I created a HTTP Server for file handling, means you can upload file and delete them from anywhere ***only if your are connected to same network i.e., same Wifi/mobile network.***


### Split Up of Code...

#### First part is Configuring the System to required setup.

```
ENC = sys.stdout.encoding
ENC_MAP = {"cp936": "gbk"}
CHARSET = ENC_MAP.get(ENC, "utf-8")

reload(sys)
sys.setdefaultencoding("utf-8")

logging.basicConfig(
    level=logging.INFO,
    format="[%(asctime)s] [%(levelname)s] - %(message)s",
    datefmt="%Y-%m-%d %H:%M:%S",
)

FILE_NAME = os.path.basename(__file__).split('.')[0]
WORK_PATH = sys.argv[2] if sys.argv[2:] else os.getcwd()
```

#### Next part is HTML code to create a interface on the web which makes upload and delete files easier.

#### Next File Handling, means accessing the files from your local system. Here you can edit which directory You want (Default: Current Directory).

#### Http Request Handling, here the protocol communication ocuurs requesting and processing the response.

#### The main function----
    
      Here I am creating a socket for connection and then using multithreading concepts.
      whenever a new connection is made it creates one thread and run it. 
      So you can make simultaneous connections.

# Usage
```
  > python http_server.py [port]
  or
  > python http_server.py 
        this takes a default port 8000
  -- For pc/laptop open web browser and type localhost:[port](default:8000)
  -- For mobile open browser and type the  systems ip adress:port number [example: 198.19.12.34:8000]
```
- All the details will be stored in a json file. It is automatically created by code itself.

# Screenshots

> PC ScreenShot

![Screenshot](https://user-images.githubusercontent.com/47880398/67833086-a26f6e80-fb09-11e9-91c8-d77099456524.png)

> Mobile Screenshot

![Screenshot1](https://user-images.githubusercontent.com/47880398/67833640-3a218c80-fb0b-11e9-9aba-6ae75d70ec49.png)
