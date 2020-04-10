# EC2 Instance Launch Types
* **On Demand Instances**: short workload, predictable pricing
* **Reserved Instances**: long workloads, > 1 year
* **Convertible Reserved Instances**: long workloads with flexible instance types
* **Scheduled Reserved Instances**: launch within a time window you reserve
* **Spot Instances**: short workloads, for cheap, can loose instances
* **Dedicated Instances**: no other customers will share your hardware
* **Dedicated Hosts**: book an entire physical server, control instance placement

## On Demand Instances
* Pay for what you use. Billed per second after the first minute
* Highest cost but no up front payment
* No long term commitment
* Recommended for short-term and uninterrupted workloads, where you can't predict how the app will behave

## Reserved Instances
* Up to 75% discount compared to on-demand
* Pay upfront for what you use with long term commitment
* Reservation period of 1 year or 3 years
* Reserve specific instance type
* Recommended for steady-state apps (think database)

## Convertible Reserved Instances
* Can change instance type
* Up to 54% discount

## Scheduled Reserved Instances
* Launch within time window you reserve
* For example: every weekend for the football game

## Spot Instances
* Up to 90% discount
* Bid on prices
* Prices vary based on demand
* You get 2 minute warning when prices exceeds your maximum bid
* Batch jobs, data analysis, workloads that are resilient to failures

## Dedicated Hosts
* Physical dedicated EC2 server
* Control of EC2 Instance placement
* Visibility into underlying sockets and physical cores of hardware
* Allocated for 3 year period
* Useful for:
    * Software that has complicated licenses (BYOL- Bring Your Own License)
    * Strong regulatory compliance

## Dedicated Instances
* Running on hardware that is dedicated to you
* No control of hardware
* May share hardware with other instances in same account
* If you start/stop Dedicated Instances, they may change hardware