# LSTS - Svelte Remake
## _Local Stock Tracking System_

This is a remake of [LSTS](https://github.com/Gater73/LSTS) made with sveltekit and using a api that gets data from MongoDB.
<br>
<img height=50 href="https://www.typescriptlang.org/" src="https://upload.wikimedia.org/wikipedia/commons/thumb/4/4c/Typescript_logo_2020.svg/2048px-Typescript_logo_2020.svg.png"/>
<img height=50 href="mongodb.com" src="https://i.imgur.com/GcMb0SQ.png"/>

Tracks the stock of local pharmacies to help people find their medicine easier

- Track items availability in drug stores near you
- Spend less time searching for the right place to get your meds
- Helps you use your time with more efficiency

## Valuable information
- This version is written in Svelte (Typescript) and is not complete nor secure.
- This version needs a api that returns a special json to function, a example api code in python using flask:
```python
from flask import Flask, jsonify
from flask_pymongo import PyMongo
from flask_cors import CORS
from pymongo.errors import PyMongoError

app = Flask(__name__)
app.config['MONGO_URI'] = 'MONGODB_CONNECT_STRING'
mongo = PyMongo(app)

@app.route('/api/<unit>', methods=['GET'])
def get_documents(unit):
    try:
        collection = mongo.db.remedios
        documents = collection.find({'unit': unit})

        result = []
        for doc in documents:
            result.append({
                '_id': str(doc['_id']),
                'name': doc['name'],
                'quant': doc['quant']
            })

        return jsonify(result)
    except PyMongoError as e:
        return str(e), 500

if __name__ == '__main__':
        CORS(app)
        app.run(host='localhost', port=8888)
```

## Features

- Automagically gets the latest availability data and prices

## Warning
> :warning: **This is a PoC project for educational purposes only**: We don't provide any support, use at your own risk!

## Important

- LSTS - Svelte Ramake requires Svelte, NPM

## Run
```sh
npm run dev -- --open
```

## License

[GPL v3](https://www.gnu.org/licenses/gpl-3.0.en.html)

[//]: # (Thanks SO - http://stackoverflow.com/questions/4823468/store-comments-in-markdown-syntax)

   [Name]: <Link>
