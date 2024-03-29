# links
[Fanout Code] (https://gist.github.com/k0emt/1218497/d5fe2ac6f7c17fc6fd3e62fa690e2fdac7e06c87)

[Fanout] (https://www.cloudamqp.com/blog/rabbitmq-fanout-exchange-explained.html)

[Exchanges] (https://tedblob.com/category/java/rabbitmq/)

# Architecture
Publisher -> RabbitMQ (VH->exchange)
Subcriber_1 (test1) <- RabbitMQ (VH->xxchange)
Subcriber_2 (test2) <- RabbitMQ (VH->xxchange)


# RabbitMQ Management

## test
- curl -i -u guest:guest http://localhost:15672/api/vhosts

## Browser
http://localhost:15672
guest/guest

## notes
- There are several types of exchanges. The fanout exchange ignores the routing key and sends messages to all queues. But pretty much all other exchange types use the routing key to determine which queue, if any, will receive a message.

- Use Topic & Direct Exchanges (routing key) to bind topic/key to queues. One queue can take mulitple topics/key.

# Python
- python3 fanout_publisher_subscriber.py receive test1
- python3 fanout_publisher_subscriber.py receive test2
- python3 fanout_publisher_subscriber.py send