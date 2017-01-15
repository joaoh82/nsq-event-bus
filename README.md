## Event Bus NSQ

* A tiny wrapper around [go-nsq](https://github.com/nsqio/go-nsq) topic and channel.

## Installation
```go
go get -u https://github.com/rafaeljesus/nsq-event-bus
```

## Environment Variables
```bash
export NSQ_URL=localhost:4151
export NSQ_LOOKUPD_URL=localhost:4151
```

## Usage
The nsq-event-bus package exposes a interface for emitting and listening events.

### Emitter
```go
import "github.com/rafaeljesus/nsq-event-bus"

topic := "events"
var event struct{}
eventBus, _ := eventbus.NewEventBus()

if err := eventBus.Emit(topic, &event); err != nil {
  // handle failure to emit message
}

```

### Listener
```go
import "github.com/rafaeljesus/nsq-event-bus"

topic := "events"
metricsChannel := "metrics"
notificationsChannel := "notifications"
eventBus, _ := eventbus.NewEventBus()

if err := eventBus.On(topic, metricsChannel); err != nil {
  // handle failure to listen a message
}

if err := eventBus.On(topic, notificationsChannel); err != nil {
  // handle failure to listen a message
}

```

## Contributing
- Fork it
- Create your feature branch (`git checkout -b my-new-feature`)
- Commit your changes (`git commit -am 'Add some feature'`)
- Push to the branch (`git push origin my-new-feature`)
- Create new Pull Request

## Badges

[![Build Status](https://circleci.com/gh/rafaeljesus/nsq-event-bus.svg?style=svg)](https://circleci.com/gh/rafaeljesus/nsq-event-bus)
[![Go Report Card](https://goreportcard.com/badge/github.com/rafaeljesus/nsq-event-bus)](https://goreportcard.com/report/github.com/rafaeljesus/nsq-event-bus)

---

> GitHub [@rafaeljesus](https://github.com/rafaeljesus) &nbsp;&middot;&nbsp;
> Medium [@_jesus_rafael](https://medium.com/@_jesus_rafael) &nbsp;&middot;&nbsp;
> Twitter [@_jesus_rafael](https://twitter.com/_jesus_rafael)
