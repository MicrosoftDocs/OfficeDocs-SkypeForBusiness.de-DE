---
title: Verwalten der zweistufigen Authentifizierung in Skype for Business Server 2015
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.date: 12/20/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 16f08710-8961-4659-acbf-ebb95a198fb4
description: 'Zusammenfassung: Verwalten der zweistufigen Authentifizierung in Skype für Business Server 2015.'
ms.openlocfilehash: 5933afc311514e841d7fb96f41988d8f495d0bee
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/28/2018
---
# <a name="manage-two-factor-authentication-in-skype-for-business-server-2015"></a><span data-ttu-id="cabec-103">Verwalten der zweistufigen Authentifizierung in Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="cabec-103">Manage two-factor authentication in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="cabec-104">**Zusammenfassung:** Verwalten der zweistufigen Authentifizierung in Skype für Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="cabec-104">**Summary:** Manage two-factor authentication in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="cabec-105">Die zweistufige Authentifizierung bietet eine verbesserte Sicherheit, indem gefordert wird, dass Benutzer zwei Authentifizierungskriterien erfüllen: eine Kombination aus Benutzername und Kennwort sowie ein Token oder Zertifikat.</span><span class="sxs-lookup"><span data-stu-id="cabec-105">Two-factor authentication provides improved security by requiring users to provide two forms of authentication or identification, namely a user name/password combination and a token or certificate.</span></span> <span data-ttu-id="cabec-106">Dies ist auch als "etwas, das Sie haben, etwas, den Sie kennen."</span><span class="sxs-lookup"><span data-stu-id="cabec-106">This is also known as "something you have, something you know."</span></span> 
  
<span data-ttu-id="cabec-p102">Ein typisches Beispiel für eine zweistufige Authentifizierung ist die Nutzung von Smartcards. Eine Smartcard enthält ein Zertifikat, das einem Benutzerkonto zugewiesen ist und welches mit den Benutzer- und Zertifikatinformationen überprüft werden kann, die auf einem Server gespeichert sind. Durch Abgleichen der Benutzerinformationen (Benutzername und Kennwort) mit dem bereitgestellten Zertifikat überprüft der Server die Anmeldeinformationen, sodass er den Benutzer authentifizieren kann.</span><span class="sxs-lookup"><span data-stu-id="cabec-p102">A typical example of two-factor authentication with a certificate is the use of smart cards. A smart card contains a certificate associated with the user account, and can be validated against user and certificate information stored on a server. By comparing the user information (user name and password) to the certificate provided, the server validates the credentials and authenticates the user.</span></span>
  
<span data-ttu-id="cabec-110">Beachten Sie die folgenden Betreffzeilen, bei einer Skype für Business Server 2015 Umgebung zur Unterstützung der zweistufigen Authentifizierung zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="cabec-110">Consider the following subjects when configuring a Skype for Business Server 2015 environment to support two-factor authentication.</span></span>
  
## <a name="client-support"></a><span data-ttu-id="cabec-111">Clientunterstützung</span><span class="sxs-lookup"><span data-stu-id="cabec-111">Client Support</span></span>

<span data-ttu-id="cabec-112">Das kumulative Updates für Lync Server 2013: Juli 2013 Desktopclient und der Skype für Business-Client sind die einzigen Clients, die derzeit zweistufigen Authentifizierung unterstützen.</span><span class="sxs-lookup"><span data-stu-id="cabec-112">The Cumulative Updates for Lync Server 2013: July 2013 desktop client and the Skype for Business client are the only clients that currently support two-factor authentication.</span></span>
  
## <a name="topology-requirements"></a><span data-ttu-id="cabec-113">Anforderungen im Hinblick auf die Topologie</span><span class="sxs-lookup"><span data-stu-id="cabec-113">Topology Requirements</span></span>

<span data-ttu-id="cabec-114">Kunden werden dringend empfohlen, die zweistufige Authentifizierung mit dedizierten Skype für Business Server 2015 Edge, Director und Pools für Benutzer bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="cabec-114">Customers are strongly encouraged to deploy two-factor authentication using dedicated Skype for Business Server 2015 with Edge, Director, and User Pools.</span></span> <span data-ttu-id="cabec-115">Um passiven Authentifizierung für Benutzer aktivieren möchten, müssen für andere Rollen und Dienste, einschließlich der folgenden beiden Authentifizierungsmethoden deaktiviert werden:</span><span class="sxs-lookup"><span data-stu-id="cabec-115">To enable passive authentication for users, other authentication methods must be disabled for other roles and services, including the following:</span></span>
  
|<span data-ttu-id="cabec-116">**Konfigurationstyp**</span><span class="sxs-lookup"><span data-stu-id="cabec-116">**Configuration Type**</span></span>|<span data-ttu-id="cabec-117">**Diensttyp**</span><span class="sxs-lookup"><span data-stu-id="cabec-117">**Service Type**</span></span>|<span data-ttu-id="cabec-118">**Serverrolle**</span><span class="sxs-lookup"><span data-stu-id="cabec-118">**Server Role**</span></span>|<span data-ttu-id="cabec-119">**Authentifizierungstyp für deaktivieren**</span><span class="sxs-lookup"><span data-stu-id="cabec-119">**Authentication Type to Disable**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="cabec-120">Webdienst</span><span class="sxs-lookup"><span data-stu-id="cabec-120">Web Service</span></span>  <br/> |<span data-ttu-id="cabec-121">WebServer</span><span class="sxs-lookup"><span data-stu-id="cabec-121">WebServer</span></span>  <br/> |<span data-ttu-id="cabec-122">Director</span><span class="sxs-lookup"><span data-stu-id="cabec-122">Director</span></span>  <br/> |<span data-ttu-id="cabec-123">Kerberos, NTLM und Zertifikat</span><span class="sxs-lookup"><span data-stu-id="cabec-123">Kerberos, NTLM, and Certificate</span></span>  <br/> |
|<span data-ttu-id="cabec-124">Webdienst</span><span class="sxs-lookup"><span data-stu-id="cabec-124">Web Service</span></span>  <br/> |<span data-ttu-id="cabec-125">WebServer</span><span class="sxs-lookup"><span data-stu-id="cabec-125">WebServer</span></span>  <br/> |<span data-ttu-id="cabec-126">Front-End</span><span class="sxs-lookup"><span data-stu-id="cabec-126">Front End</span></span>  <br/> |<span data-ttu-id="cabec-127">Kerberos, NTLM und Zertifikat</span><span class="sxs-lookup"><span data-stu-id="cabec-127">Kerberos, NTLM, and Certificate</span></span>  <br/> |
|<span data-ttu-id="cabec-128">Proxy</span><span class="sxs-lookup"><span data-stu-id="cabec-128">Proxy</span></span>  <br/> |<span data-ttu-id="cabec-129">EdgeServer</span><span class="sxs-lookup"><span data-stu-id="cabec-129">EdgeServer</span></span>  <br/> |<span data-ttu-id="cabec-130">Edge</span><span class="sxs-lookup"><span data-stu-id="cabec-130">Edge</span></span>  <br/> |<span data-ttu-id="cabec-131">Kerberos und NTLM</span><span class="sxs-lookup"><span data-stu-id="cabec-131">Kerberos and NTLM</span></span>  <br/> |
|<span data-ttu-id="cabec-132">Proxy</span><span class="sxs-lookup"><span data-stu-id="cabec-132">Proxy</span></span>  <br/> |<span data-ttu-id="cabec-133">Registrierungsstelle</span><span class="sxs-lookup"><span data-stu-id="cabec-133">Registrar</span></span>  <br/> |<span data-ttu-id="cabec-134">Front-End</span><span class="sxs-lookup"><span data-stu-id="cabec-134">Front End</span></span>  <br/> |<span data-ttu-id="cabec-135">Kerberos und NTLM</span><span class="sxs-lookup"><span data-stu-id="cabec-135">Kerberos and NTLM</span></span>  <br/> |
   
<span data-ttu-id="cabec-136">Sofern diese Authentifizierungstypen nicht auf Dienstebene deaktiviert sind, ist es mit keiner anderen Version des Clients möglich, sich erfolgreich anzumelden, sobald die zweistufige Authentifizierung in Ihrer Bereitstellung aktiviert wurde.</span><span class="sxs-lookup"><span data-stu-id="cabec-136">Unless these authentication types are disabled at the service level, all other versions of the client will be unable to sign in successfully once two-factor authentication is enabled within in your deployment.</span></span>
  
## <a name="skype-for-business-service-discovery"></a><span data-ttu-id="cabec-137">Ermittlung der Skype for Business-Services</span><span class="sxs-lookup"><span data-stu-id="cabec-137">Skype for Business Service Discovery</span></span>

<span data-ttu-id="cabec-138">DNS-Einträge, die von internen oder externen Clients zum Ermitteln von Skype für BusinessServices verwendet sollte so konfiguriert werden, einen Skype für Business Server erläutern, die für die zweistufige Authentifizierung nicht aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="cabec-138">DNS records used by internal and/or external clients to discover Skype for Business services should be configured to resolve to a Skype for Business server that is not enabled for two-factor authentication.</span></span> <span data-ttu-id="cabec-139">Mit dieser Konfiguration werden Benutzer von Skype für Business-Pools, die nicht für die zweistufige Authentifizierung aktiviert sind nicht aufgefordert werden, geben eine PIN authentifiziert, während Benutzer von Skype für Business-Pools, die für die zweistufige Authentifizierung aktiviert sind, erforderlich, um ihre PIN zur Authentifizierung eingeben.</span><span class="sxs-lookup"><span data-stu-id="cabec-139">With this configuration, users from Skype for Business Pools that are not enabled for two-factor authentication will not be required to enter a PIN to authenticate, while users from Skype for Business Pools that are enabled for two-factor authentication will be required to enter their PIN to authenticate.</span></span>
  
## <a name="exchange-authentication"></a><span data-ttu-id="cabec-140">Exchange-Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="cabec-140">Exchange Authentication</span></span>

<span data-ttu-id="cabec-141">Kunden, die zweistufige Authentifizierung für Microsoft Exchange bereitgestellt haben möglicherweise fest, dass bestimmte Features im-Client nicht verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="cabec-141">Customers who have deployed two-factor authentication for Microsoft Exchange may find that certain features in the client are unavailable.</span></span> <span data-ttu-id="cabec-142">Dies ist derzeit konzipiert, die Skype für Business Client zweistufigen Authentifizierung für die Features nicht unterstützt, die Exchange-Integration abhängig sind.</span><span class="sxs-lookup"><span data-stu-id="cabec-142">This is currently by design, as the Skype for Business client does not support two-factor authentication for features that are dependent on Exchange integration.</span></span>
  
## <a name="contacts"></a><span data-ttu-id="cabec-143">Kontakte</span><span class="sxs-lookup"><span data-stu-id="cabec-143">Contacts</span></span>

<span data-ttu-id="cabec-144">Skype für Unternehmensbenutzer, die konfiguriert sind, um das Feature Unified Contact Store nutzen werden feststellen, dass ihre Kontakte nach der Anmeldung mit zweistufiger Authentifizierung nicht mehr verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="cabec-144">Skype for Business users who are configured to leverage the Unified Contact Store feature will find that their contacts are no longer available after signing in with two-factor authentication.</span></span>
  
<span data-ttu-id="cabec-145">Verwenden Sie das Cmdlet " **Invoke-CsUcsRollback** ", vorhandene Benutzerkontakte aus der einheitliche Kontaktspeicher entfernt und in Skype für Business Server 2015 vor der Aktivierung der zweistufigen Authentifizierung speichern.</span><span class="sxs-lookup"><span data-stu-id="cabec-145">You should use the **Invoke-CsUcsRollback** cmdlet to remove existing user contacts from the Unified Contact Store and store them in Skype for Business Server 2015 before enabling two-factor authentication.</span></span>
  
## <a name="skill-search"></a><span data-ttu-id="cabec-146">Qualifikationssuche</span><span class="sxs-lookup"><span data-stu-id="cabec-146">Skill Search</span></span>

<span data-ttu-id="cabec-147">Kunden, die das Feature für die Suche nach Fertigkeiten in ihren Skype für geschäftsumgebung konfiguriert haben werden feststellen, dass dieses Feature nicht funktioniert, wenn Skype für Unternehmen für die zweistufige Authentifizierung aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="cabec-147">Customers who have configured the Skill Search feature in their Skype for Business environment will find that this feature does not work when Skype for Business is enabled for two-factor authentication.</span></span> <span data-ttu-id="cabec-148">Dies ist entwurfsbedingt, weil Microsoft SharePoint momentan die zweistufige Authentifizierung nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="cabec-148">This is by design, as Microsoft SharePoint does not currently support two-factor authentication.</span></span>
  
## <a name="credentials"></a><span data-ttu-id="cabec-149">Anmeldeinformationen</span><span class="sxs-lookup"><span data-stu-id="cabec-149">Credentials</span></span>

<span data-ttu-id="cabec-150">Es gibt eine Reihe von Bereitstellungsaspekte im Zusammenhang mit gespeicherten Skype für Business Anmeldeinformationen an, die Benutzern auswirkt, die für die Verwendung der zweistufigen Authentifizierung konfiguriert sind.</span><span class="sxs-lookup"><span data-stu-id="cabec-150">There are a number of deployment considerations involving saved Skype for Business credentials which may impact users who are configured to use two-factor authentication.</span></span>
  
### <a name="deleting-saved-credentials"></a><span data-ttu-id="cabec-151">Löschen von gespeicherten Anmeldeinformationen</span><span class="sxs-lookup"><span data-stu-id="cabec-151">Deleting Saved Credentials</span></span>

<span data-ttu-id="cabec-152">Benutzer sollten verwenden die Option **Meine Info - Anmeldung löschen** in der Skype für Business-Client und Löschen von ihre SIP-Profilordner aus %localappdata%\Microsoft\Office\15.0\Skype für Business vor dem Signieren zum ersten Mal mit zwei Faktoren Authentifizierung.</span><span class="sxs-lookup"><span data-stu-id="cabec-152">Users should use the **Delete my sign-in info** option in the Skype for Business client and delete their SIP profile folder from %localappdata%\Microsoft\Office\15.0\Skype for Business before attempting to sign for the first time using two-factor authentication.</span></span>
  
### <a name="disablentcredentials"></a><span data-ttu-id="cabec-153">DisableNTCredentials</span><span class="sxs-lookup"><span data-stu-id="cabec-153">DisableNTCredentials</span></span>

<span data-ttu-id="cabec-154">Mit der Kerberos- oder NTLM-Authentifizierungsmethode werden automatisch die Windows-Anmeldeinformationen des Benutzers für die Authentifizierung verwendet.</span><span class="sxs-lookup"><span data-stu-id="cabec-154">With the Kerberos or NTLM authentication method, the user's Windows credentials are used automatically for authentication.</span></span> <span data-ttu-id="cabec-155">In einer typischen Skype für Business Server 2015 Bereitstellung, in denen Kerberos- und/oder NTLM für die Authentifizierung aktiviert ist, sollten Benutzer keinen ihre Anmeldeinformationen jedes Mal eingeben, die Anmeldung.</span><span class="sxs-lookup"><span data-stu-id="cabec-155">In a typical Skype for Business Server 2015 deployment where Kerberos and/or NTLM is enabled for authentication, users should not have to enter their credentials every time that they sign in.</span></span>
  
<span data-ttu-id="cabec-156">Werden Benutzer unbeabsichtigt zur Eingabe ihrer Anmeldeinformationen aufgefordert, bevor sie zur Eingabe ihrer PIN aufgefordert werden, ist möglicherweise versehentlich der Registrierungsschlüssel **DisableNTCredentials** auf Clientcomputern konfiguriert (möglicherweise über eine Gruppenrichtlinie).</span><span class="sxs-lookup"><span data-stu-id="cabec-156">If users are unintentionally prompted for credentials before they are prompted to enter their PIN, the **DisableNTCredentials** registry key may be unintentionally configured on client computers, possibly through Group Policy.</span></span>
  
<span data-ttu-id="cabec-157">Um weitere Aufforderung zur erneuten Eingabe zu verhindern, erstellen Sie den folgenden Registrierungswert auf dem lokalen Computer oder der Skype für administrative Vorlage für Business auf alle Benutzer für einen bestimmten Pool mithilfe von Gruppenrichtlinien anwenden:</span><span class="sxs-lookup"><span data-stu-id="cabec-157">To prevent the additional prompt for credentials, create the following registry entry on the local workstation or use the Skype for Business administrative template to apply to all users for a given pool using Group Policy:</span></span>
  
    HKEY_LOCAL_MACHINE\Software\Policies\Microsoft\Office\15.0\Lync
  
    REG_DWORD: DisableNTCredentials
  
    Value: 0x0
  
### <a name="savepassword"></a><span data-ttu-id="cabec-158">SavePassword</span><span class="sxs-lookup"><span data-stu-id="cabec-158">SavePassword</span></span>

<span data-ttu-id="cabec-159">Wenn ein Benutzer bei Skype für Unternehmen zum ersten Mal anmeldet, wird der Benutzer aufgefordert, um das Kennwort zu speichern.</span><span class="sxs-lookup"><span data-stu-id="cabec-159">When a user signs in to Skype for Business for the first time, the user is prompted to save his or her password.</span></span> <span data-ttu-id="cabec-160">Wenn ausgewählt haben, kann diese Option des Benutzers Client-Zertifikat in den persönlichen Zertifikatspeicher und Windows-Anmeldeinformationen des Benutzers, in dem Anmeldeinformations-Manager des lokalen Computers gespeichert werden sollen gespeichert werden.</span><span class="sxs-lookup"><span data-stu-id="cabec-160">If selected, this option allows the user's client certificate to be stored in the personal certificate store and the user's Windows credentials to be stored in the Credential Manager of the local computer.</span></span>
  
<span data-ttu-id="cabec-161">Die Einstellung der Registrierung **SavePassword** sollte deaktiviert werden, wenn Skype für Unternehmen zur Unterstützung der zweistufigen Authentifizierung konfiguriert ist.</span><span class="sxs-lookup"><span data-stu-id="cabec-161">The **SavePassword** registry setting should be disabled when Skype for Business is configured to support two-factor authentication.</span></span> <span data-ttu-id="cabec-162">Um zu verhindern, dass Benutzer ihre Kennwörter speichern, ändern Sie den folgenden Registrierungswert auf der lokalen Arbeitsstation, oder verwenden Sie die Skype für administrative Vorlage für Business auf alle Benutzer für einen bestimmten Pool mithilfe von Gruppenrichtlinien anwenden:</span><span class="sxs-lookup"><span data-stu-id="cabec-162">To prevent users from saving their passwords, change the following registry entry on the local workstation or use the Skype for Business administrative template to apply to all users for a given pool using Group Policy:</span></span>
  
    HKEY_CURRENT_USER\Software\Microsoft\Office\15.0\Lync
  
    REG_DWORD: SavePassword
  
    Value: 0x0
  
## <a name="ad-fs-20-token-replay"></a><span data-ttu-id="cabec-163">AD FS 2.0-Tokenwiederholung</span><span class="sxs-lookup"><span data-stu-id="cabec-163">AD FS 2.0 Token Replay</span></span>

<span data-ttu-id="cabec-p110">AD FS 2.0 stellt eine Funktion bereit, die als Tokenwiederholungserkennung bezeichnet wird und mit welcher mehrere Tokenanforderungen, in denen dasselbe Token verwendet wird, erkannt und verworfen werden können. Ist diese Funktion aktiviert, schützt die Tokenwiederholungserkennung die Integrität von Authentifizierungsanforderungen sowohl im passiven WS-Federation-Profil als auch im SAML WebSSO-Profil, indem sichergestellt wird, dass ein Token nie mehrmals verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="cabec-p110">AD FS 2.0 provides a feature referred to as token replay detection, by which multiple token requests using the same token can be detected and then discarded. When this feature is enabled, token replay detection protects the integrity of authentication requests in both the WS-Federation passive profile and the SAML WebSSO profile by making sure that the same token is never used more than once.</span></span>
  
<span data-ttu-id="cabec-166">Diese Funktion sollte in Umgebungen aktiviert sein, in denen Sicherheit einen besonders hohen Stellenwert hat, beispielsweise bei der Nutzung von Kiosken.</span><span class="sxs-lookup"><span data-stu-id="cabec-166">This feature should be enabled in situations where security is a very high concern such as when using kiosks.</span></span> <span data-ttu-id="cabec-167">Weitere Informationen zu token wiedergabeschutzes finden Sie unter [Bewährte Methoden für die Secure Planung und Bereitstellung von AD FS 2.0](https://go.microsoft.com/fwlink/p/?LinkId=309215).</span><span class="sxs-lookup"><span data-stu-id="cabec-167">For more information about token replay detection, see [Best Practices for Secure Planning and Deployment of AD FS 2.0](https://go.microsoft.com/fwlink/p/?LinkId=309215).</span></span>
  
## <a name="external-user-access"></a><span data-ttu-id="cabec-168">Zugriff von externen Benutzern</span><span class="sxs-lookup"><span data-stu-id="cabec-168">External User Access</span></span>

<span data-ttu-id="cabec-169">Konfigurieren eines AD FS-Proxy oder Reverseproxy zur Unterstützung der Skype für Business zweistufigen Authentifizierung von externen Netzwerken wird in diesen Themen nicht behandelt.</span><span class="sxs-lookup"><span data-stu-id="cabec-169">Configuring an ADFS Proxy or Reverse Proxy to support Skype for Business two-factor authentication from external networks is not covered in these topics.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="cabec-170">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="cabec-170">See also</span></span>

#### 

[<span data-ttu-id="cabec-171">Konfigurieren der zweistufigen Authentifizierung in Skype für Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="cabec-171">Configure two-factor authentication in Skype for Business Server 2015</span></span>](configure.md)
  
[<span data-ttu-id="cabec-172">Konfigurieren der zweistufigen Authentifizierung in Skype für Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="cabec-172">Configure two-factor authentication in Skype for Business Server 2015</span></span>](configure.md)

