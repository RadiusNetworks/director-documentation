# Director Documentation

Designed to help developers manage their beacon fleet. Director provides status
and management of your proximity beacon network. It does this by leveraging
both a management mobile app and crowdsourced information from your app
installed on users mobile devices.

Director provides a scalable, cloud-based system where you can view the status
of all beacons, manage the metadata that helps you identify where they are
located and alerts you when they need attention.

<h2> Activating Director </h1>
To begin to monitor beacon status in your Director Dashboard, integrate our Campaign Kit or Proximity Kit SDK with your mobile app, and then follow the steps below:

<b> Activating Director After Proximity Kit Integration </b>
<br>
After integrating Proximity Kit for iOS or/and Android by following the steps detailed <a href= "https://proximitykit.radiusnetworks.com/docs/overview"> here </a>, follow the steps below to activate Director and begin to monitor the health status of every beacon in your fleet.

1. Login to your Radius Networks <a href="https://account.radiusnetworks.com"> Account</a> and click on "Team Settings".
2. On the "Team Settings" page, click on "New Team", enter the "Team Name" and click on "create".
3. From the account page, click on "Director", and select "Settings" from under the new team you just created.
4. Under "SDK Access Tokens", click on "Generate Token".
5. Copy the newly generated token.
6. Go back to the accounts home page and click on "Proximity Kit".
7. On the Proximity Kit page, click on "Create New Kit".
8. Enter you "Kit name", ensure "Explicit Beacon Monitoring" is checked and paste the "Status Token" you copied from Director.
9. Click save.

You are done! Next time your app syncs with Proximity Kit, Status Kit will be automatically enabled.

<b> Activating Director After Campaign Kit Integration </b>
<strong> TBD </strong>

## Public API Resources

The [Director API](api) provides programmable access to the rich content
about your beacon fleet. It is designed to integrate Director with other
systems. It is specifically intended to provide access to the features and
functionality available through the web interface.

## Additional Resources

- [Dashboard](https://director.radiusnetworks.com/teams)
- [API Access](https://account.radiusnetworks.com/personal_tokens)
- [Team Settings](https://account.radiusnetworks.com/teams)
- [Developer Portal](http://developer.radiusnetworks.com)

---

## Still need a hand?

If you have any other questions feel free to drop us a [note](mailto:support@radiusnetworks.com).
