#POC of Shipping Booking Micro-Service Notes

### Findings
#### we could find kafka cluster id in console
2019-03-14 14:50:19.975  INFO 19224 --- [-StreamThread-1] org.apache.kafka.clients.Metadata        : Cluster ID: vCZhXy9ITAOSI62I8-HydQ
it seems like random id. But we could alos use "primary" as cluster name since it was default cluster name for kafka. we could confirm that by using "Kafka Tool"

### Error or Excpetions
#### What if the port number of kafka to connect isn't correct ?
WARN message:
2019-03-14 14:46:02.640  WARN 6604 --- [| adminclient-1] org.apache.kafka.clients.NetworkClient   : [AdminClient clientId=adminclient-1] Connection to node -1 could not be established. Broker may not be available.
will be printed in console but will not make application failed to start.

### Questions:
#### What is kafak stream thread do ? 
Found some log in console relate to kafka stream thread
2019-03-14 14:50:19.921  INFO 19224 --- [-StreamThread-1] o.a.k.s.p.internals.StreamThread         : stream-thread [bookings_service_command-9cf849b8-ef92-457b-818c-a0635db19527-StreamThread-1] State transition from CREATED to RUNNING

#### what's consumer, what is group in kafka
2019-03-14 14:50:19.975  INFO 19224 --- [-StreamThread-1] org.apache.kafka.clients.Metadata        : Cluster ID: vCZhXy9ITAOSI62I8-HydQ

#### how to change kafka's cluster name ?