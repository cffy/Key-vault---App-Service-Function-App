	<p><strong>Using Key Vault to protect secrets &ndash; App Service / Function App</strong></p>
	<p>First step - in your app service, enable the Identity &gt; system assigned:</p>
	<img src="https://github.com/cffy/ImageGlobalRepos/blob/main/Key vault - App service/1.jpg" alt="FME">
	<p>Then, go to Key Vault and create the secrets that you&rsquo;ll need, in my case for the scenario, I only needed two:</p>
	<p>Image2</p>
	<p>Open the secrets and save the URI, you will need the value in a next step:</p>
	<p>Image3</p>
	<p>&nbsp;</p>
	<p>Click on the CURRENT VERSION &gt; Copy the URI for all the secrets you need and paste to a txt file:</p>
	<p>Image4</p>
	<p>Image5</p>
	<p>Then, also in the Key Vault, go to Access Policies and allow your App Service to access to the Key Vault:</p>
	<p>&nbsp;</p>
	<p>Click on Add Access Policy:</p>
	<p>Image6</p>
	<p>&nbsp;</p>
	<p>Select Key &amp; Secret Management:</p>
	<p>Image7</p>
	<p>&nbsp;</p>
	<p>Select Get and List:</p>
	<p>Image8</p>
	<p>&nbsp;</p>
	<p>Click on Select principal and paste the name of your App Service (web app) and click on Add:</p>
	<p>Image9</p>
	<p>&nbsp;</p>
	<p>Then your app will be able to get and list the secrets from the Key Vault.</p>
	<p>&nbsp;</p>
	<p>Check in the Access Policies to see if the configuration was successful.</p>
	<p>Image10</p>
	<p>&nbsp;</p>
	<p>Always save to apply the changes.</p>
	<p>&nbsp;</p>
	<p>Return to your App Service (Web App) and go to the configuration.</p>
	<p>Here you will create two app settings to call the secrets from the Key Vault. You can use the name of your preference.</p>
	<p>Image11</p>
	<p>In my case I named them app-password and user-password, the value is extremely case sensitive app-password = @Microsoft.KeyVault(SecretUri=This we got this Uri in previous steps and is in your txt file).</p>
	<p>@Microsoft.KeyVault(SecretUri=https://keyvaultcase.vault.azure.net/secrets/apppassword/62dc01bXXXXXXXXXXXXXXXXXXXXXXa67f)</p>
	<p>Save to apply the new app settings, if the value was well configured you will see the source with a green check in the Key Vault reference.</p>
	<p>Image13</p>
	<p>Image14</p>
	<p>Image15</p>
	<p>&nbsp;</p>
	<p>Now you can use the secrets in your code, it works exactly as the .evn settings, since this app settings are configured to be part of the ENVIROMENT VARIABLES.</p>
	<p>&nbsp;</p>
	<p>&nbsp;</p>
	<p>Here is a small guide how to use it.</p>
	<p>The project:</p>
	<p>Image16</p>
	<p>Image17</p>
	<p>&nbsp;</p>
