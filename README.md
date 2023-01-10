<p><strong>Using Key Vault to protect secrets &ndash; App Service / Function App</strong></p>
<p>First step - in your app service, enable the Identity &gt; system assigned:</p>
<img src="https://github.com/cffy/ImageGlobalRepos/blob/main/Key vault - App service/1.jpg" alt="FME">
<p>Then, go to Key Vault and create the secrets that you&rsquo;ll need, in my case for the scenario, I only needed two:</p>
<img src="https://github.com/cffy/ImageGlobalRepos/blob/main/Key vault - App service/2.jpg" alt="FME">
<p>Open the secrets and save the URI, you will need the value in a next step:</p>
<img src="https://github.com/cffy/ImageGlobalRepos/blob/main/Key vault - App service/3.jpg" alt="FME">
<p>Click on the CURRENT VERSION &gt; Copy the URI for all the secrets you need and paste to a txt file:</p>
<img src="https://github.com/cffy/ImageGlobalRepos/blob/main/Key vault - App service/4.jpg" alt="FME">
<img src="https://github.com/cffy/ImageGlobalRepos/blob/main/Key vault - App service/5.jpg" alt="FME">
<p>Then, also in the Key Vault, go to Access Policies and allow your App Service to access to the Key Vault:</p>
<p>&nbsp;</p>
<p>Click on Add Access Policy:</p>
<img src="https://github.com/cffy/ImageGlobalRepos/blob/main/Key vault - App service/6.jpg" alt="FME">
<p>&nbsp;</p>
<p>Select Key &amp; Secret Management:</p>
<img src="https://github.com/cffy/ImageGlobalRepos/blob/main/Key vault - App service/7.jpg" alt="FME">
<p>&nbsp;</p>
<p>Select Get and List:</p>
<img src="https://github.com/cffy/ImageGlobalRepos/blob/main/Key vault - App service/8.jpg" alt="FME">
<p>&nbsp;</p>
<p>Click on Select principal and paste the name of your App Service (web app) and click on Add:</p>
<img src="https://github.com/cffy/ImageGlobalRepos/blob/main/Key vault - App service/9.jpg" alt="FME">
<p>&nbsp;</p>
<p>Then your app will be able to get and list the secrets from the Key Vault.</p>
<p>&nbsp;</p>
<p>Check in the Access Policies to see if the configuration was successful.</p>
<img src="https://github.com/cffy/ImageGlobalRepos/blob/main/Key vault - App service/10.jpg" alt="FME">
<p>&nbsp;</p>
<p>Always save to apply the changes.</p>
<p>&nbsp;</p>
<p>Return to your App Service (Web App) and go to the configuration.</p>
<p>Here you will create two app settings to call the secrets from the Key Vault. You can use the name of your preference.</p>
<img src="https://github.com/cffy/ImageGlobalRepos/blob/main/Key vault - App service/11.jpg" alt="FME">
<p>In my case I named them app-password and user-password, the value is extremely case sensitive app-password = @Microsoft.KeyVault(SecretUri=This we got this Uri in previous steps and is in your txt file).</p>
<p>@Microsoft.KeyVault(SecretUri=https://keyvaultcase.vault.azure.net/secrets/apppassword/62dc01bXXXXXXXXXXXXXXXXXXXXXXa67f)</p>
<p>Save to apply the new app settings, if the value was well configured you will see the source with a green check in the Key Vault reference.</p>
<img src="https://github.com/cffy/ImageGlobalRepos/blob/main/Key vault - App service/12.jpg" alt="FME">
<img src="https://github.com/cffy/ImageGlobalRepos/blob/main/Key vault - App service/13.jpg" alt="FME">
<img src="https://github.com/cffy/ImageGlobalRepos/blob/main/Key vault - App service/14.jpg" alt="FME">
<p>&nbsp;</p>
<p>Now you can use the secrets in your code, it works exactly as the .evn settings, since this app settings are configured to be part of the ENVIROMENT VARIABLES.</p>
<p>&nbsp;</p>
<p>Here is a small guide how to use it.</p>
<p>The project:</p>
<img src="https://github.com/cffy/ImageGlobalRepos/blob/main/Key vault - App service/15.jpg" alt="FME">
<img src="https://github.com/cffy/ImageGlobalRepos/blob/main/Key vault - App service/16.jpg" alt="FME">
<img src="https://github.com/cffy/ImageGlobalRepos/blob/main/Key vault - App service/17.jpg" alt="FME">
<p>&nbsp;</p>
<div id="footer" align="center">
  <p>&nbsp;</p>
  <p>______________________________________________________________________________________</p>
  <p><p>&nbsp;</p>
  <a href="mailto:joycascante@gmail.com"><img src="https://cdn.pixabay.com/photo/2016/01/10/22/52/letters-1132703_960_720.png" width="60"/></a>
  <a href="#"> <img src="https://www.practicepanther.com/wp-content/uploads/2016/06/linkedin-for-lawyers.png" width="60" alt="LinkedIn Badge"/></a>
  </p>
  <p>__________________________________________________________________</p>
  <p>Last post update: Jan 10, 2023.</p>
</div>
