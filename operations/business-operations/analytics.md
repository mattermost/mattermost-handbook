---
description: 'Owner: Rachel Bradley-Haas'
---

# Analytics

Business Operations, Data Engineering, and Analytics functions were started in December and are ever evolving. Because of how new we are, eveything on this page is currently WIP.

We are currently focused on:
* Data collection
* Mapping data to business logic
* Data modeling
* Looker (data visualization tool replacing Chartio)
* Automating Metrics


## Metrics
### Mattermost Top Line Numbers

#### ARR (Annual Recurring Revenue)

* ARR is the value of the contracted recurring revenue components of your term subscriptions normalized to a one-year period.
* `ARR = (Total Contract Value / (End Date - Start Date)) * 365`
* [ARR Overview in Looker](Link): 

* Monthly ARR increases and decreases based on the following categories of change 
  * New: New Logo never seen before.
  * Expansion: Increase in ARR by an Account. This is caused by seat increase, price increase, or product upgrade.
  * Contraction: Decrease in ARR by an Account. This is caused by seat decrease, price decrease, or product downgrade.
  * Churn: Decrease in ARR to $0 by an Account. This is caused by an Account moving completely off of Mattermost.
* [ARR Monthly Net Changes](https://mattermost.looker.com/looks/2?toggle=det): This look breaks down the Monthly ARR Net Changes by the four categories above.

#### Downloads
