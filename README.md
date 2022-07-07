# azure
Azure bicep code

Bicep werkwijze:

Creëer een bicep template met de gewenste functionaliteit, voorbeelden zijn te vinden op:

Azure resource reference - Bicep & ARM template reference | Microsoft Docs

Deploy  het template vervolgens in een nieuwe ResourceGroup:

<code>
  az group create --name exampleRG --location westeurope
  az deployment group create --resource-group exampleRG --template-file main.bicep --parameters adminUsername=<admin-username>
</code>

Review deployed resources:

<code>
  az resource list --resource-group exampleRG
</code>

Aanpassen van de deployment, maak een aanpassing in het template (bijv. vmSize)
Eerst een what-if run om te controleren wat zou worden aangepast:

<code>
  az deployment group what-if --resource-group exampleRG --template-file main.bicep --parameters adminUsername=<admin-username>
</code>

Indien akkoord, deployen:

<code>
  az deployment group create --resource-group exampleRG --template-file main.bicep --parameters adminUsername=<admin-username>
</code>

Clean up resources:

<code>
  az group delete --name exampleRG
</code>

[![Deploy to Azure](https://aka.ms/deploytoazurebutton)](https://portal.azure.com/#create/Microsoft.Template/uri/https%3A%2F%2Fgithub.com%2Fcmeerendonk%2Fazure%2Fraw%2Fmain%2Fvm.json)

[![Deploy to Azure](https://aka.ms/deploytoazurebutton)](https://portal.azure.com/#create/Microsoft.Template/uri/https%3a%2f%2fraw.githubusercontent.com%2fAzure%2fazure-quickstart-templates%2fmaster%2fquickstarts%2fmicrosoft.compute%2fvm-simple-linux%2fazuredeploy.json)
