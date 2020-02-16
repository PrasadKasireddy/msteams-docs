## Prerequisites

- To complete this quickstart you'll need an Office 365 tenant and a team configured with *Allow uploading custom apps* enabled. To learn more, see [Prepare your Office 365 tenant](~/concepts/build-and-test/prepare-your-o365-tenant.md).
  - If you don't currently have an Office 365 account, you can sign up for a free subscription through the [Office 365 Developer Program](/OfficeDev/office-dev-program-docs/docs/office-365-developer-program). The subscription will remain active as long as you're using it for ongoing development.

- You'll use App Studio to import your application to Teams. To install App Studio select **Apps** ![Store App](~/assets/images/tab-images/storeApp.png) at the bottom-left corner of the Teams app, and search for App Studio. Once you find the tile, select it and choose install in the pop-up window dialog box.

In addition, this project requires that you have the following installed in your development environment:

- The current version the Visual Studio IDE with the **.NET CORE cross-platform development** workload installed. If you don't already have Visual Studio, you can download and install the latest [Microsoft Visual Studio Community](https://visualstudio.microsoft.com/downloads) version for free.

- The [ngrok](https://ngrok.com) reverse proxy tool. You'll use ngrok to create a tunnel to your locally running web server's publicly-available HTTPS endpoints. You can [download it here](https://ngrok.com/download).
