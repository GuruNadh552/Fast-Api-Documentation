# Fast API

#### Requirements : 

 - **Python 3+** ( preferred )

#### Modules : 

 - **Uvicorn**  ( pip install uvicorn or python3 -m pip install uvicorn )

 - **fastapi** ( pip install fastapi or python3 -m pip install fastapi )
 
### Steps :

- Firstly we need to import **fastapi** and intiialize an app

``` python
from typing import Optional

from fastapi import FastAPI

app = FastAPI()

```

- we can save in .py extension and run the file using uvicorn in cmd or terminal

```
uvicorn FileName:app or python3 -m uvicorn Filename:app
```

- Mostly we will created API's based on  GET.POST,PUT and DELETE Requests

#### Simple GET Request Example 

``` python
from typing import Optional

from fastapi import FastAPI

app = FastAPI()


@app.get("/")
def get_data():
    return {"Hello": "World"}
```

#### Simple POST Request
``` python
from typing import Optional

from fastapi import FastAPI,Request

app = FastAPI()


@app.get("/")
def post_data(req: Request):
    data = await req.json()
    #apply some operations on data
    return response
```
- import corsMiddle 

- when you get any CORS while reteriving data or posting data then add the following origins in your python file

```
from typing import Optional

from fastapi import FastAPI,Request

from fastapi.middleware.cors import CORSMiddleware

app = FastAPI()

origins = ["*"]

app.add_middleware(
    CORSMiddleware,
    allow_origins=origins,
    allow_credentials=True,
    allow_methods=["*"],
    allow_headers=["*"],
)
```

### Delete , put are same as POST request
