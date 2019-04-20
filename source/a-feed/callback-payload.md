# The Callback Payload

Route4Me immediately submits a payload to your [Activity Feed's callback URL][1] each time it detects a [supported activity or event][2] that occurred either from your account or anyone from your team members.

The payload is a JSON object that represents or associates with the activity that just occurred. Route4Me submits a payload for each event that happened.

Below is an example from a "Route Optimized" activity.

```
{
  "optimization_problem_id":"AY803F567829383C659BB81DEE5DEAX3",
  "route_id":"BCCBB11E0DA5B793C7A9B10C54443344",
  "member_id":"110111",
  "activity_type":"route-optimized",
  "activity_id":"8D10678B2BACCB72D923FDA5B178C96M",
  "activity_timestamp":0588977903,
  "activity_message":"Directions prepared for route 'Supermarket Deliveries'",
  "remote_ip":0,
  "day_id":3376,
  "device_type":"web",
  "root_owner_member_id":"110111",
  "activity_day_id":3376,
  "account_type_id":"126",
  "member_level":0,
  "root_owner_member_api_key":"AXD8A3DD49FB3271C88897F49C3F9699",
  "root_owner_member_email":"john_doe@route4me.com"
}
```

Now, the properties of the JSON object vary depending on the activity. Some activities either have more or fewer features than others. But no matter what event occurred, the common properties are always present. Here's a list of them:

|Key|Description|
|:--|:----------|
|activity_id|The ID of the activity or event that occurred.|
|activity_type|Short name for the activity that occurred. It can be one of the constant strings used to describe [the activities logged by the Activity Feed][2].|
|activity_message|Describes and provides information about the activity that occurred.|
|activity_timestamp|The time, in Unix Epoch, when the activity occurred.|
|member_id|The member or user ID of the user that initiated the activity.|
|device_type|The device used by the user to run the Route4Me application (web or mobile) and initiate the activity that occurred.|
|remote_ip|The IP address of the computer.|
|day_id|An integer value that serves as the ID of the day the activity occurred.|
|activity_day_id|Value is similar to the value of the `day_id` property.|
|account_type_id|The ID representing the account type.|
|member_level|A number indicating a user's level. It's `0` for account owners, while a non-zero value for [other user types][3].|
|root_owner_member_id|The account owner's member ID.<br><br>The account owner is the top-level user who owns the Route4Me account and to whom the subscription is billed. All other types of users (Administrator, Route Planner, Driver, etc.) are under or belongs to this user.|
|root_owner_member_api_key|The account owner's API key.|
|root_owner_member_email|The account owner's email.|

Among the properties listed above, the useful ones are `activity_type`, `activity_message`, and `member_id`.

The `activity_type` property helps you identify [what activity the payload is associated with][2], and because of it, it's considered as the most useful of all the properties. Your callback URL can programmatically filter for this property so that you can process and respond accordingly only to the activities you are interested in.

As an example, let's say you want your Route4Me workflow to make use of [Twilio's SMS service][4] to send you text messages every time a driver of yours [leaves and marks each of his or her destinations as "Mark as Visited"][5]. To do this, the code that processes the payload in your callback URL must check for the `mark-destination-visited` value of the `activity_type` property. After that, use Twilio's SMS API to send a text message to your phone.

Now, the other two useful properties mentioned earlier are `activity_message` and `member_id`. These properties provide a detailed description of the activity and the ID of the Route4Me user that initiated it, respectively.

Lastly, it's worth mentioning that most supported activities are related to route-specific operations. Their payload generally has a `route_id` property and depending on the specific event, includes either a `route_destination_id` or `optimization_problem_id` property. These properties will come in handy if ever you decide to use or access the endpoints of the [Route resource][6] of the [Route4Me Platform API][7]. 

The main takeaway in working with the payload is familiarity with the activity that sent it and knowing the properties you need so that you can respond according to your desired workflow.


[1]:    provide-callback-url.md
[2]:    supported-activities.md

[3]:    https://support.route4me.com/managing-users-and-team-members/

[4]:    https://www.twilio.com/sms
[5]:    https://support.route4me.com/tracking-route-progress-ipad/

[6]:    https://route4me.io/docs/#routes
[7]:    https://route4me.io/docs/#platform-apis
