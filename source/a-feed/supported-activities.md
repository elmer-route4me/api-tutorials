# Activity Types List

Here's a list of Route4Me activities or events that are supported and logged by the Activity Feed. Keep in mind that these activities don't account for all the actions that could be done in a Route4Me account. They are merely a fraction of it.

Included for each activity is the constant string value of the `activity_type` property when you receive [the callback payload][1] from [your Activity Feed's callback URL][2] and with a description of how the activity came about.


|No.|Activity Type|Constant String|Description|
|--:|:------------|:---------------|:---------|
|1|Remove Avoidance Zone|"area-removed"|Triggered/logged when removing an existing avoidance zone.|
|2|Create New Avoidance Zone|"area-added"|Triggered when adding/creating a new avoidance zone.|
|3|Edit Avoidance Zone|"area-updated"|Triggered when updating (renaming, changing points) an existing avoidance zone.|
|4|Remove Address From Route|"delete-destination"|Triggered when [deleting/removing an address or stop within a route][14].|
|5|Add New Address|"insert-destination"|Triggered when [adding a new stop within a route][15].|
|6|Route Deviation|"destination-out-sequence"|Triggered when a driver marks an address as visited before any other ones before it in the sequence. This means that the driver didn't follow the series of addresses in a route.|
|7|User Arrived Early|"driver-arrived-early"|Triggered when a driver arrives early at an address and marks it as "visited".|
|8|User Arrived Late|"driver-arrived-late"|Triggered when a driver arrives late at an address and marks it as "visited".|
|9|User Arrived On Time|"driver-arrived-on-time"|Triggered when a driver arrives on time at an address and marks it as "visited".|
|10|Geofence Triggered Check Out|"geofence-left"|Triggered when a driver leaves a [geofenced area][16].|
|11|Geofence Triggered Check In|"geofence-entered"|Triggered when a driver enters a geofenced area.|
|12|Mark Address Departed|"mark-destination-departed"|Triggered when an address is marked as "departed".|
|13|Mark Address Visited|"mark-destination-visited"|Triggered when an address is marked as "visited".|
|14|Created Team Member|"member-created"|Triggered when [creating a new user][5].|
|15|Delete Team Member|"member-deleted"|Triggered when deleting an existing user.|
|16|Modified Member|"member-modified"|Triggered when updating the details of an existing user.|
|17|Change Address Sequence|"move-destination"|Triggered when manually [changing the order or sequence of a stop][6] within a route.|
|18|Note Insert|"note-insert"|Triggered when [adding a note to a stop or address][7] within a route.|
|19|Delete Route|"route-delete"|Triggered when [removing/deleting a route][13].|
|20|Route Optimized |"route-optimized"|Triggered when manually [reoptimizing a route][8] or [refreshing its directions][10]. Also triggered when reordering the sequence of stops or addresses within a route.|
|21|Assigned Other User To Route|"route-owner-changed"|Triggered when [assigning a user to an existing route][12].|
|22|Route Duplication|"route-duplicate"|Triggered when [duplicating an existing route][11].|
|23|Update Address Attribute|"update-destinations"|Triggered when you add custom data to an address.|
|24|User Message|"user_message"|Triggered when a user communicates or chats with its team members using the [Two-Way Real-Time Chat][3] feature or through a custom application that uses the [Activity Feed resource][4] of the Route4Me API.|
|25|Route Merging|"route-merge"|Triggered when two or more [routes are consolidated to create one route][9].|
|26|Rename Route|"route-update"| Triggered when [renaming a route][17].|
|27|Approved To Execute|"approved-to-execute"| Triggered when a user approves a route to start executing.|


[1]:    callback-payload.md
[2]:    provide-callback-url.md
[3]:    https://support.route4me.com/team-communication-with-the-two-way-real-time-chat/
[4]:    https://route4me.io/docs/#log-a-specific-message

[5]:    https://support.route4me.com/managing-users-and-team-members/

[6]:    https://support.route4me.com/changing-the-order-of-addresses-in-a-planned-route/

[7]:    https://support.route4me.com/viewing-and-adding-notes-in-the-route-editor/

[8]:    https://support.route4me.com/re-optimizing-a-route/

[9]:    https://support.route4me.com/merging-multiple-routes-at-the-same-time/

[10]:   https://support.route4me.com/refreshing-the-directions-of-a-route/

[11]:   https://support.route4me.com/duplicating-routes/

[12]:   https://support.route4me.com/assigning-users-and-vehicles-to-routes/

[13]:   https://support.route4me.com/deleting-routes/

[14]:   https://support.route4me.com/deleting-addresses-from-an-existing-route/

[15]:   https://support.route4me.com/inserting-an-address-into-a-route-from-the-route-editor/

[16]:   https://support.route4me.com/setting-automatic-visitation-triggers-and-viewing-your-geofence-activities/

[17]:   https://support.route4me.com/renaming-a-route/
