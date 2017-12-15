## Namespace To Rabbit

This is one component of the scraping architecture.

Currently, this component:

#. Gets pages of names within a namespace
#. Gets the zonefile for each name
#. Publishes the name+zonefile in a message to RabbitMQ.

Any name that returns an unexpected zonefile (one not starting with
`'$ORIGIN'`) is ignored. Any names that have fail to retrieve a zonefile
are ignored.

### Setup
Install app dependencies with:
```
yarn
```

or
```
npm install
```

Then, make sure you have a RabbitMQ instance available:
```
docker-compose up
```
will do the trick. If you already have one running, ensure that the
rabbit host and exchange are configured properly in `config.json`.

Run the app with:
```
yarn run dev
```
or
```
npm run dev
```