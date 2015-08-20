# Sidekiq Opsworks Cookbook using upstart

Inspiration from https://github.com/drakerlabs/opsworks_sidekiq
Inspiration from https://github.com/bargeapp/opsworks-sidekiq


## Configuration
In stack settings set custom json like so:

```
"sidekiq": {
  "APP_NAME" {
    "instances": "1",
    "concurrency": "25",
    "queues": [
      "low",
      ["high", 7]
    ],
    "rack_env": "production"
  }
}
```

## Usage

1. `opsworks-sidekiq::setup` for setup
2. `opsworks-sidekiq::restart` for deploy