# Calabrio Integration
Integration with Calabrios WFM tool consists of four main parts: 
 1. Tenant setup - at the beggining the tenant will need to stet up with agent information, queue information, roles, etc... This information will need to be migrated into the system.
 2. Realtime data - realtime data on current workload and agent availabilty.
 3. Historical data - data used to analyse performance and workload in previous periods, e.g - previous queue loads and ticket resolution times.
 4. Forecast imports - as we have decided not to use Calabrios forecasting solution, but we would still like to use their forecast viewing solution, the forecasts would need to be uploaded to Calabrio daily.

## Infrastructure
The integration will be based from a serverless function. 

## Tenant setup
Basic agent information can be added to the system using a simple file import. Skills, however, will have to be updated for each agent using an API.
The API can be found [here](https://mtdemousce01.teleopticloud.com/api/docs/index.html#/Commands/POST_command_AddSkillsToPerson)

## Historical data
Historical data is sent in three parts:
1. Agent-Queue stats - Sent per agent-per queue and contains data about the interactions performed by an agent in a specific queue during a given interval.
2. Agent stats - Sent per agent and contains data related to the agents work accross all queues duringa given interval.
3. Queue stats - Sent per queue and contains data related to the work load on the queue and the quality of service in the given interval.

These stats will be taken from the interactions table, will use an interval of 1 hour and will be sent to Calabrio once daily.
APIs for all three can be found [here](https://mtdemousce01.teleopticloud.com/historical-data/docs/index.html).

## Realtime data

## Forecast imports
