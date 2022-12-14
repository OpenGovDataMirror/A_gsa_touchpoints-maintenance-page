# Touchpoints Maintenance Page

This app is used to display a Maintenance page for the
Touchpoints application. When Touchpoints undergoes maintenance,
this application is served instead of the
Touchpoints web application on Cloud.gov.

This app is a one-page static .html file, deployed as an app to Cloud.gov.

For more context on when and how this page is used, see
https://github.com/GSA/touchpoints/wiki/Deployment.

### Commands

These commands assume we're using Touchpoints' Staging environment,
with `touchpoints-staging-maintenance` as the Maintenance Page app name,
and `touchpoints-staging` as the web application app name.
We're also assuming our Cloud Foundry instance is `app.cloud.gov`.
Be sure to update your app names and CF instance accordingly.

To create a Maintenance Page, run the following command from the [maintenance repo](https://github.com/gsa/touchpoints-maintenance-page).
`cf push touchpoints-staging-maintenance -m 64M --no-route`

To toggle a page on
`cf map-route touchpoints-staging-maintenance app.cloud.gov --hostname touchpoints-staging`

To toggle a page off
`cf unmap-route touchpoints-staging-maintenance app.cloud.gov --hostname touchpoints-staging`
Then,
`cf map-route touchpoints-staging app.cloud.gov --hostname touchpoints-staging`
