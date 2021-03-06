---
swagger: "2.0"
x-collection-name: Datadog
x-complete: 0
info:
  title: DataDog API Add Tags Hosts Host Name
  version: 1.0.0
  description: This end point allows you to add tags to a host.
basePath: api/v1/
schemes:
- http
produces:
- application/json
consumes:
- application/json
paths:
  /metrics:
    get:
      summary: Get Metrics
      description: Get the list of actively reporting metrics from a given time until
        now. This endpoint is not available in the Python and Ruby libraries.
      operationId: getMetrics
      x-api-path-slug: metrics-get
      responses:
        200:
          description: OK
      tags:
      - Monitoring
      - Metrics
  /series:
    post:
      summary: Add Series
      description: |-
        The metrics end-point allows you to post time-series data that can be
                  graphed on Datadog's dashboards.
      operationId: postSeries
      x-api-path-slug: series-post
      parameters:
      - in: query
        name: '[[POSIX_timestamp, numeric_value], ...]'
        description: Note that the timestamp should be in seconds, must be current,
          and the numeric value is a 32bit float gauge-type value
        type: string
      responses:
        200:
          description: OK
      tags:
      - Monitoring
      - Series
  /query:
    get:
      summary: Get Query
      description: This end point allows you to query for metrics from any time period.
      operationId: getQuery
      x-api-path-slug: query-get
      responses:
        200:
          description: OK
      tags:
      - Monitoring
      - Query
  /check_run:
    post:
      summary: Add Check Run
      description: Post a Check Run
      operationId: postCheckRun
      x-api-path-slug: check-run-post
      responses:
        200:
          description: OK
      tags:
      - Monitoring
      - Checks
      - Run
  /downtime:
    post:
      summary: Add Downtime
      description: Schedule monitor downtime
      operationId: postDowntime
      x-api-path-slug: downtime-post
      parameters:
      - in: query
        name: period
        description: how often to repeat as an integer
        type: string
      - in: query
        name: type
        description: the type of recurrence
        type: string
      - in: query
        name: until_date
        description: (optional) the date at which the recurrence should end as a POSIX
          timestmap
        type: string
      - in: query
        name: until_occurrences
        description: (optional) how many times the downtime will be rescheduled
        type: string
      - in: query
        name: week_days
        description: (optional) a list of week days to repeat on
        type: string
      responses:
        200:
          description: OK
      tags:
      - Monitoring
      - Downtime
    get:
      summary: Get Downtime
      description: Get all monitor downtimes
      operationId: getDowntime
      x-api-path-slug: downtime-get
      responses:
        200:
          description: OK
      tags:
      - Monitoring
      - Downtime
  /downtime/:downtime_id:
    put:
      summary: Put Downtime Downtime
      description: Update monitor downtime
      operationId: putDowntimeDowntime
      x-api-path-slug: downtimedowntime-id-put
      parameters:
      - in: query
        name: period
        description: how often to repeat as an integer
        type: string
      - in: query
        name: type
        description: the type of recurrence
        type: string
      - in: query
        name: until_date
        description: (optional) the date at which the recurrence should end as a POSIX
          timestmap
        type: string
      - in: query
        name: until_occurrences
        description: (optional) how many times the downtime will be rescheduled
        type: string
      - in: query
        name: week_days
        description: (optional) a list of week days to repeat on
        type: string
      responses:
        200:
          description: OK
      tags:
      - Monitoring
      - Downtime
      - Downtime
    delete:
      summary: Delete Downtime Downtime
      description: DELETE downtime downtime
      operationId: deleteDowntimeDowntime
      x-api-path-slug: downtimedowntime-id-delete
      responses:
        200:
          description: OK
      tags:
      - Monitoring
      - Downtime
      - Downtime
    get:
      summary: Get Downtime Downtime
      description: Get a monitor downtime
      operationId: getDowntimeDowntime
      x-api-path-slug: downtimedowntime-id-get
      responses:
        200:
          description: OK
      tags:
      - Monitoring
      - Downtime
      - Downtime
  /screen:
    post:
      summary: Add Screen
      description: POST screen
      operationId: postScreen
      x-api-path-slug: screen-post
      responses:
        200:
          description: OK
      tags:
      - Monitoring
      - Screen
    get:
      summary: Get Screen
      description: Fetch all of your screenboards' definitions.
      operationId: getScreen
      x-api-path-slug: screen-get
      responses:
        200:
          description: OK
      tags:
      - Monitoring
      - Screen
  /screen/:board_id:
    put:
      summary: Put Screen Board
      description: PUT screen board
      operationId: putScreenBoard
      x-api-path-slug: screenboard-id-put
      responses:
        200:
          description: OK
      tags:
      - Monitoring
      - Screen
      - Board
    delete:
      summary: Delete Screen Board
      description: Delete an existing screenboard.
      operationId: deleteScreenBoard
      x-api-path-slug: screenboard-id-delete
      responses:
        200:
          description: OK
      tags:
      - Monitoring
      - Screen
      - Board
    get:
      summary: Get Screen Board
      description: Fetch an existing screenboard's definition.
      operationId: getScreenBoard
      x-api-path-slug: screenboard-id-get
      responses:
        200:
          description: OK
      tags:
      - Monitoring
      - Screen
      - Board
  /screen/share/:board_id:
    get:
      summary: Get Screen Share Board
      description: Share an existing screenboard's with a public URL.
      operationId: getScreenShareBoard
      x-api-path-slug: screenshareboard-id-get
      responses:
        200:
          description: OK
      tags:
      - Monitoring
      - Screen
      - Share
      - Board
    delete:
      summary: Delete Screen Share Board
      description: Revoke a currently shared screenboard's.
      operationId: deleteScreenShareBoard
      x-api-path-slug: screenshareboard-id-delete
      responses:
        200:
          description: OK
      tags:
      - Monitoring
      - Screen
      - Share
      - Board
  /tags/hosts:
    get:
      summary: Get Tags Hosts
      description: Return a mapping of tags to hosts for your whole infrastructure.
      operationId: getTagsHosts
      x-api-path-slug: tagshosts-get
      responses:
        200:
          description: OK
      tags:
      - Monitoring
      - Tags
      - Hosts
  /tags/hosts/:host_name:
    get:
      summary: Get Tags Hosts Host Name
      description: Return the list of tags that apply to a given host.
      operationId: getTagsHostsHostName
      x-api-path-slug: tagshostshost-name-get
      responses:
        200:
          description: OK
      tags:
      - Monitoring
      - Tags
      - Hosts
      - Host
      - Name
    post:
      summary: Add Tags Hosts Host Name
      description: This end point allows you to add tags to a host.
      operationId: postTagsHostsHostName
      x-api-path-slug: tagshostshost-name-post
      responses:
        200:
          description: OK
      tags:
      - Monitoring
      - Tags
      - Hosts
      - Host
      - Name
x-streamrank:
  polling_total_time_average: 0
  polling_size_download_average: 0
  streaming_total_time_average: 0
  streaming_size_download_average: 0
  change_yes: 0
  change_no: 0
  time_percentage: 0
  size_percentage: 0
  change_percentage: 0
  last_run: ""
  days_run: 0
  minute_run: 0
---