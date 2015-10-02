# docker-fluentd-s3

this command will route all containers outputs to a kinesis stream:
```
	docker run --name logger -d \
		-e AWS_KEY=key \
		-e AWS_SECRET=secret \
		-e KINESIS_STREAM_NAME=stream1 \
		-e KINESIS_PARTITION_KEY=pkey \
		-e KINESIS_REGION=us-east-1 \
		-v /var/lib/docker/containers:/var/lib/docker/containers \
		-v /var/log/docker:/var/log/docker \
		tmuskal/fluentd-kinesis
```