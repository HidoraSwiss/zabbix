### Custom script to add Hostname on Summary field in pagerduty Webhook.

Use it with : https://www.zabbix.com/fr/integrations/pagerduty

Replace script in your pager duty media with this one.

  ![media_script](media_script.png "media_script")


To change summary feild on pagerduty event, you can modify :

          fields.payload = {
              summary: params.hostname + " -- " + params.eventname,
              source: (params.event_source === '1') ? 'Discovery' : params.hostname + ' : ' + params.hostip,
              severity: severityMapping[params.severity],
          };
          
          
  ![event_example](event_example.png "event_example")
  
