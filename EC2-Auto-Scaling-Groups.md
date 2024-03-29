## Auto-Scaling Groups

![](https://docs.aws.amazon.com/autoscaling/ec2/userguide/images/sample-3-tier-architecture-with-azs-diagram.png)

* Can be created from a Launch Template or Configuration.
* Instance distribution
    * Amazon EC2 Auto Scaling attempts to distribute instances evenly between the Availability Zones that are enabled for your Auto Scaling group.
* Rebalancing
    * Availability Zone rebalancing
        *  The following actions can lead to rebalancing activity:
            * You change the Availability Zones for your group.
            * You explicitly terminate or detach instances and the group becomes unbalanced.
            * An Availability Zone that previously had insufficient capacity recovers and has additional capacity available.
            * An Availability Zone that previously had a Spot price above your maximum price now has a Spot price below your maximum price.
    * Capacity Rebalancing
        * When you turn on Capacity Rebalancing, Amazon EC2 Auto Scaling attempts to launch a Spot Instance whenever Amazon EC2 notifies that a Spot Instance is at an elevated risk of interruption.
* Scaling options:
    * Maintain current instance levels at all times.
        * Desired capacity = minimum capacity = maximum capacity.
    * Scale manually.
        * Increase desired and/or maximum capacity.
    * Predictive scaling
        * Predictive scaling builds a forecast based on historical data and scales out capacity in advance of forecasted hourly load, so that new instances are ready to handle traffic when the load arrives.
        * Based on target usage.
        * CPU utilisation, Network in (bytes), Network out (bytes), or Custom metric pair.
    * Dynamic scaling
        * A dynamic scaling policy instructs Amazon EC2 Auto Scaling to track a specific CloudWatch metric, and it defines what action to take when the associated CloudWatch alarm is in ALARM.
        * Target tracking scaling.
            * Based on target usage.
            * CPU utilisation, Network in (bytes), Network out (bytes), or Load balancer request count.
        * Step scaling.
            * Based on CloudWatch alarm.
            * Set to, Add, or Remove.
            * Can define multiple steps.
        * Simple scaling.
            * Based on CloudWatch alarm.
            * Set to, Add, or Remove.
    * Scheduled scaling.
        * Change desired, max, and min based on a schedule.
* Notifications
    * Can be sent to an SNS topics.
    * For the following events:
        * Launch
        * Terminate
        * Fail to launch
        * Fail to terminate
* Lifecyle Hooks
    * Lifecycle hooks enable an Auto Scaling group to be aware of events in the Auto Scaling instance lifecycle, and then perform a custom action when the corresponding lifecycle event occurs. A lifecycle hook provides a specified amount of time (one hour by default) to complete the custom action before the instance transitions to the next state.

### Launch Configuration 

* Note. AWS strongly recommend using Launch Templates instead of Launch Configurations.

### Launch Templates

* A launch template is similar to a launch configuration, in that it specifies instance configuration information. 
* Unlike launch configurations, launch templates are versioned.

### Creating a Launch Template

Requires the following comfiguration:

* AMI
* Instance type
* Key Pair (login)
* Subnet (in which to locate ENI)
* Security Group
* Network Interfaces
* EBS Volumes


What happens if you don't specify Instance Type, Key Pair, Subnet, Network Interface,  


