# Regions
Regions are what they sound like. Clusters of servers located in geographically distinct regions.

# Availability Zones (AZ)
Availability zones are physically separated data centres within a region

```
us-west-2b
^        ^
|        |
|        AZ
Region
```

# AWS Console
The AWS Console is region scoped. The region can be selected in the upper right. IAM and S3 are exceptions and are global scoped.