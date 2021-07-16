# Setting up Kafka (and Zookeeper) on docker-compose


Source : https://gist.github.com/rmoff/fb7c39cc189fc6082a5fbd390ec92b3d

To setup and use kafka in docker compose locally,

0. Install `kafkacat` (https://github.com/edenhill/kafkacat) to use as a kafka client
1. Start docker compose `docker-compose up .`. Change port numbers from the default `29092` if you would like to.
2. Set topic name `TOPIC=general`
3. Publish to the topic using `kafkacat` (input can be piped in via `stdin` OR provided interactively at the terminal). The topic will be created if it does not exit.
   ```
   kafkacat -P -b localhost:29092 -t $TOPIC
   ```
4. Test that it can be consumed from the topic using `kafkacat`
   ```
   kafkacat -b localhost:29092 -t $TOPIC
   ```