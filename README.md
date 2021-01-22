# RabbitMQ Management Action

This Action sets up a RabbitMQ instance with management options. It is possible to set up the `username`, `password`, `port`, `management port` and `image tag` in the Action options. This was developed to be used with the [wait-for-http](https://github.com/mer-team/wait-for-http) Docker Image that allows us to wait for the RabbitMQ service start and then run the tests.

## Inputs
| Arg | Default | Description |
| --- | --- | --- |
| RABBITMQ_USER | guest | RabbitMQ Username |
| RABBITMQ_PASS | guest | RabbitMQ Password  |
| RABBITMQ_PORT | 5672 | RabbitMQ Port |
| RABBITMQ_MNG_PORT | 15672 | RabbitMQ Management Port |
| RABBITMQ_TAG | 3-alpine | RabbitMQ Docker Image Tag |

To be able to access the management API you should use a Docker Image tag with Management (not used by default). You can check all the available RabbitMQ Docker Image Tags [here](https://hub.docker.com/_/rabbitmq/)

## Usage
```yaml
steps:
- uses: merteam/rabbitmq-mng-action/@v1.0
  with:
    RABBITMQ_USER: 'username'
    RABBITMQ_PASS: 'password'
    RABBITMQ_PORT: 5672
    RABBITMQ_MNG_PORT: 15672
    RABBITMQ_TAG: '3management-alpine'
```