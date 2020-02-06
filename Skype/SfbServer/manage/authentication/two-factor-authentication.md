---
title: Verwalten der zweistufigen Authentifizierung in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 16f08710-8961-4659-acbf-ebb95a198fb4
description: 'Zusammenfassung: Verwalten der zweistufigen Authentifizierung in Skype for Business Server.'
ms.openlocfilehash: 90dc286e247c0c6eeb75bb884071b85e57663278
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41818717"
---
# <a name="manage-two-factor-authentication-in-skype-for-business-server"></a><span data-ttu-id="9bb5d-103">Verwalten der zweistufigen Authentifizierung in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="9bb5d-103">Manage two-factor authentication in Skype for Business Server</span></span>
 
<span data-ttu-id="9bb5d-104">**Zusammenfassung:** Verwalten Sie die zweistufige Authentifizierung in Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="9bb5d-104">**Summary:** Manage two-factor authentication in Skype for Business Server.</span></span>
  
<span data-ttu-id="9bb5d-105">Die zweistufige Authentifizierung bietet eine verbesserte Sicherheit, indem gefordert wird, dass Benutzer zwei Authentifizierungskriterien erfüllen: eine Kombination aus Benutzername und Kennwort sowie ein Token oder Zertifikat.</span><span class="sxs-lookup"><span data-stu-id="9bb5d-105">Two-factor authentication provides improved security by requiring users to provide two forms of authentication or identification, namely a user name/password combination and a token or certificate.</span></span> <span data-ttu-id="9bb5d-106">Dies ist auch bekannt als "etwas, das Sie haben, etwas, das Sie kennen."</span><span class="sxs-lookup"><span data-stu-id="9bb5d-106">This is also known as "something you have, something you know."</span></span> 
  
<span data-ttu-id="9bb5d-p102">Ein typisches Beispiel für eine zweistufige Authentifizierung ist die Nutzung von Smartcards. Eine Smartcard enthält ein Zertifikat, das einem Benutzerkonto zugewiesen ist und welches mit den Benutzer- und Zertifikatinformationen überprüft werden kann, die auf einem Server gespeichert sind. Durch Abgleichen der Benutzerinformationen (Benutzername und Kennwort) mit dem bereitgestellten Zertifikat überprüft der Server die Anmeldeinformationen, sodass er den Benutzer authentifizieren kann.</span><span class="sxs-lookup"><span data-stu-id="9bb5d-p102">A typical example of two-factor authentication with a certificate is the use of smart cards. A smart card contains a certificate associated with the user account, and can be validated against user and certificate information stored on a server. By comparing the user information (user name and password) to the certificate provided, the server validates the credentials and authenticates the user.</span></span>
  
<span data-ttu-id="9bb5d-110">Berücksichtigen Sie bei der Konfiguration einer Skype for Business Server-Umgebung die folgenden Themen, um die zweistufige Authentifizierung zu unterstützen.</span><span class="sxs-lookup"><span data-stu-id="9bb5d-110">Consider the following subjects when configuring a Skype for Business Server environment to support two-factor authentication.</span></span>
  
## <a name="client-support"></a><span data-ttu-id="9bb5d-111">Clientunterstützung</span><span class="sxs-lookup"><span data-stu-id="9bb5d-111">Client Support</span></span>

<span data-ttu-id="9bb5d-112">Die kumulativen Updates für lync Server 2013: Juli 2013-Desktop Client und der Skype for Business-Client sind die einzigen Clients, die derzeit die zweistufige Authentifizierung unterstützen.</span><span class="sxs-lookup"><span data-stu-id="9bb5d-112">The Cumulative Updates for Lync Server 2013: July 2013 desktop client and the Skype for Business client are the only clients that currently support two-factor authentication.</span></span>
  
## <a name="topology-requirements"></a><span data-ttu-id="9bb5d-113">Anforderungen im Hinblick auf die Topologie</span><span class="sxs-lookup"><span data-stu-id="9bb5d-113">Topology Requirements</span></span>

<span data-ttu-id="9bb5d-114">Kunden werden dringend ermutigt, die zweistufige Authentifizierung über dedizierten Skype for Business-Server mit Edge-, Director-und User-Pools bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="9bb5d-114">Customers are strongly encouraged to deploy two-factor authentication using dedicated Skype for Business Server with Edge, Director, and User Pools.</span></span> <span data-ttu-id="9bb5d-115">Um die passive Authentifizierung für Benutzer zu aktivieren, müssen andere Authentifizierungsmethoden für andere Rollen und Dienste deaktiviert werden, einschließlich der folgenden:</span><span class="sxs-lookup"><span data-stu-id="9bb5d-115">To enable passive authentication for users, other authentication methods must be disabled for other roles and services, including the following:</span></span>
  
|<span data-ttu-id="9bb5d-116">**Konfigurationstyp**</span><span class="sxs-lookup"><span data-stu-id="9bb5d-116">**Configuration Type**</span></span>|<span data-ttu-id="9bb5d-117">**Diensttyp**</span><span class="sxs-lookup"><span data-stu-id="9bb5d-117">**Service Type**</span></span>|<span data-ttu-id="9bb5d-118">**Server Rolle**</span><span class="sxs-lookup"><span data-stu-id="9bb5d-118">**Server Role**</span></span>|<span data-ttu-id="9bb5d-119">**Zu deaktivierender Authentifizierungstyp**</span><span class="sxs-lookup"><span data-stu-id="9bb5d-119">**Authentication Type to Disable**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="9bb5d-120">Webdienst</span><span class="sxs-lookup"><span data-stu-id="9bb5d-120">Web Service</span></span>  <br/> |<span data-ttu-id="9bb5d-121">WebServer</span><span class="sxs-lookup"><span data-stu-id="9bb5d-121">WebServer</span></span>  <br/> |<span data-ttu-id="9bb5d-122">Director</span><span class="sxs-lookup"><span data-stu-id="9bb5d-122">Director</span></span>  <br/> |<span data-ttu-id="9bb5d-123">Kerberos, NTLM und Zertifikat</span><span class="sxs-lookup"><span data-stu-id="9bb5d-123">Kerberos, NTLM, and Certificate</span></span>  <br/> |
|<span data-ttu-id="9bb5d-124">Webdienst</span><span class="sxs-lookup"><span data-stu-id="9bb5d-124">Web Service</span></span>  <br/> |<span data-ttu-id="9bb5d-125">WebServer</span><span class="sxs-lookup"><span data-stu-id="9bb5d-125">WebServer</span></span>  <br/> |<span data-ttu-id="9bb5d-126">Front-End</span><span class="sxs-lookup"><span data-stu-id="9bb5d-126">Front End</span></span>  <br/> |<span data-ttu-id="9bb5d-127">Kerberos, NTLM und Zertifikat</span><span class="sxs-lookup"><span data-stu-id="9bb5d-127">Kerberos, NTLM, and Certificate</span></span>  <br/> |
|<span data-ttu-id="9bb5d-128">Proxy</span><span class="sxs-lookup"><span data-stu-id="9bb5d-128">Proxy</span></span>  <br/> |<span data-ttu-id="9bb5d-129">EdgeServer</span><span class="sxs-lookup"><span data-stu-id="9bb5d-129">EdgeServer</span></span>  <br/> |<span data-ttu-id="9bb5d-130">Edge</span><span class="sxs-lookup"><span data-stu-id="9bb5d-130">Edge</span></span>  <br/> |<span data-ttu-id="9bb5d-131">Kerberos und NTLM</span><span class="sxs-lookup"><span data-stu-id="9bb5d-131">Kerberos and NTLM</span></span>  <br/> |
|<span data-ttu-id="9bb5d-132">Proxy</span><span class="sxs-lookup"><span data-stu-id="9bb5d-132">Proxy</span></span>  <br/> |<span data-ttu-id="9bb5d-133">Registrierungsstelle</span><span class="sxs-lookup"><span data-stu-id="9bb5d-133">Registrar</span></span>  <br/> |<span data-ttu-id="9bb5d-134">Front-End</span><span class="sxs-lookup"><span data-stu-id="9bb5d-134">Front End</span></span>  <br/> |<span data-ttu-id="9bb5d-135">Kerberos und NTLM</span><span class="sxs-lookup"><span data-stu-id="9bb5d-135">Kerberos and NTLM</span></span>  <br/> |
   
<span data-ttu-id="9bb5d-136">Sofern diese Authentifizierungstypen nicht auf Dienstebene deaktiviert sind, ist es mit keiner anderen Version des Clients möglich, sich erfolgreich anzumelden, sobald die zweistufige Authentifizierung in Ihrer Bereitstellung aktiviert wurde.</span><span class="sxs-lookup"><span data-stu-id="9bb5d-136">Unless these authentication types are disabled at the service level, all other versions of the client will be unable to sign in successfully once two-factor authentication is enabled within in your deployment.</span></span>
  
## <a name="skype-for-business-service-discovery"></a><span data-ttu-id="9bb5d-137">Ermittlung der Skype for Business-Services</span><span class="sxs-lookup"><span data-stu-id="9bb5d-137">Skype for Business Service Discovery</span></span>

<span data-ttu-id="9bb5d-138">DNS-Einträge, die von internen und/oder externen Clients zur Erkennung von Skype for Business-Diensten verwendet werden, sollten so konfiguriert werden, dass Sie zu einem Skype for Business-Server aufgelöst werden, der für die zweistufige Authentifizierung nicht aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="9bb5d-138">DNS records used by internal and/or external clients to discover Skype for Business services should be configured to resolve to a Skype for Business server that is not enabled for two-factor authentication.</span></span> <span data-ttu-id="9bb5d-139">Mit dieser Konfiguration sind Benutzer aus Skype for Business-Pools, die nicht für die zweistufige Authentifizierung aktiviert sind, nicht zur Eingabe einer PIN zur Authentifizierung verpflichtet, während Benutzer aus Skype for Business-Pools, die für die zweistufige Authentifizierung aktiviert sind, erforderlich, um die PIN zur Authentifizierung einzugeben.</span><span class="sxs-lookup"><span data-stu-id="9bb5d-139">With this configuration, users from Skype for Business Pools that are not enabled for two-factor authentication will not be required to enter a PIN to authenticate, while users from Skype for Business Pools that are enabled for two-factor authentication will be required to enter their PIN to authenticate.</span></span>
  
## <a name="exchange-authentication"></a><span data-ttu-id="9bb5d-140">Exchange-Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="9bb5d-140">Exchange Authentication</span></span>

<span data-ttu-id="9bb5d-141">Kunden, die die zweistufige Authentifizierung für Microsoft Exchange bereitgestellt haben, können feststellen, dass bestimmte Features im Client nicht verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="9bb5d-141">Customers who have deployed two-factor authentication for Microsoft Exchange may find that certain features in the client are unavailable.</span></span> <span data-ttu-id="9bb5d-142">Dies ist derzeit beabsichtigt, da der Skype for Business-Client keine zweistufige Authentifizierung für Features unterstützt, die von der Exchange-Integration abhängig sind.</span><span class="sxs-lookup"><span data-stu-id="9bb5d-142">This is currently by design, as the Skype for Business client does not support two-factor authentication for features that are dependent on Exchange integration.</span></span>
  
## <a name="contacts"></a><span data-ttu-id="9bb5d-143">Kontakte</span><span class="sxs-lookup"><span data-stu-id="9bb5d-143">Contacts</span></span>

<span data-ttu-id="9bb5d-144">Skype for Business-Benutzer, die für die Nutzung des Unified Contact Store-Features konfiguriert sind, werden feststellen, dass Ihre Kontakte nach der Anmeldung mit zweistufiger Authentifizierung nicht mehr verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="9bb5d-144">Skype for Business users who are configured to leverage the Unified Contact Store feature will find that their contacts are no longer available after signing in with two-factor authentication.</span></span>
  
<span data-ttu-id="9bb5d-145">Sie sollten das Cmdlet **Invoke-CsUcsRollback** verwenden, um vorhandene Benutzer Kontakte aus dem Unified Contact Store zu entfernen und in Skype for Business Server zu speichern, bevor Sie die zweistufige Authentifizierung aktivieren.</span><span class="sxs-lookup"><span data-stu-id="9bb5d-145">You should use the **Invoke-CsUcsRollback** cmdlet to remove existing user contacts from the Unified Contact Store and store them in Skype for Business Server before enabling two-factor authentication.</span></span>
  
## <a name="skill-search"></a><span data-ttu-id="9bb5d-146">Qualifikationssuche</span><span class="sxs-lookup"><span data-stu-id="9bb5d-146">Skill Search</span></span>

<span data-ttu-id="9bb5d-147">Kunden, die die Fertigkeits Suchfunktion in Ihrer Skype for Business-Umgebung konfiguriert haben, werden feststellen, dass diese Funktion nicht funktioniert, wenn Skype for Business für die zweistufige Authentifizierung aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="9bb5d-147">Customers who have configured the Skill Search feature in their Skype for Business environment will find that this feature does not work when Skype for Business is enabled for two-factor authentication.</span></span> <span data-ttu-id="9bb5d-148">Dies ist entwurfsbedingt, weil Microsoft SharePoint momentan die zweistufige Authentifizierung nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="9bb5d-148">This is by design, as Microsoft SharePoint does not currently support two-factor authentication.</span></span>
  
## <a name="credentials"></a><span data-ttu-id="9bb5d-149">Anmeldeinformationen</span><span class="sxs-lookup"><span data-stu-id="9bb5d-149">Credentials</span></span>

<span data-ttu-id="9bb5d-150">Es gibt eine Reihe von Bereitstellungsüberlegungen für gespeicherte Skype for Business-Anmeldeinformationen, die sich auf Benutzer auswirken können, die für die Verwendung der zweistufigen Authentifizierung konfiguriert sind.</span><span class="sxs-lookup"><span data-stu-id="9bb5d-150">There are a number of deployment considerations involving saved Skype for Business credentials which may impact users who are configured to use two-factor authentication.</span></span>
  
### <a name="deleting-saved-credentials"></a><span data-ttu-id="9bb5d-151">Löschen von gespeicherten Anmeldeinformationen</span><span class="sxs-lookup"><span data-stu-id="9bb5d-151">Deleting Saved Credentials</span></span>

<span data-ttu-id="9bb5d-152">Benutzer sollten die Option **Meine Anmeldeinformationen löschen** im Skype for Business-Client verwenden und Ihren SIP-Profilordner aus%LocalAppData%\Microsoft\Office\15.0\Skype for Business löschen, bevor Sie versuchen, das erste Mal mithilfe der zweistufigen Authentifizierung zu signieren.</span><span class="sxs-lookup"><span data-stu-id="9bb5d-152">Users should use the **Delete my sign-in info** option in the Skype for Business client and delete their SIP profile folder from %localappdata%\Microsoft\Office\15.0\Skype for Business before attempting to sign for the first time using two-factor authentication.</span></span>
  
### <a name="disablentcredentials"></a><span data-ttu-id="9bb5d-153">DisableNTCredentials</span><span class="sxs-lookup"><span data-stu-id="9bb5d-153">DisableNTCredentials</span></span>

<span data-ttu-id="9bb5d-154">Bei der Kerberos-oder NTLM-Authentifizierungsmethode werden die Windows-Anmeldeinformationen des Benutzers automatisch für die Authentifizierung verwendet.</span><span class="sxs-lookup"><span data-stu-id="9bb5d-154">With the Kerberos or NTLM authentication method, the user's Windows credentials are used automatically for authentication.</span></span> <span data-ttu-id="9bb5d-155">In einer typischen Skype for Business Server-Bereitstellung, bei der Kerberos und/oder NTLM für die Authentifizierung aktiviert ist, sollten Benutzer nicht bei jeder Anmeldung Ihre Anmeldeinformationen eingeben müssen.</span><span class="sxs-lookup"><span data-stu-id="9bb5d-155">In a typical Skype for Business Server deployment where Kerberos and/or NTLM is enabled for authentication, users should not have to enter their credentials every time that they sign in.</span></span>
  
<span data-ttu-id="9bb5d-156">Werden Benutzer unbeabsichtigt zur Eingabe ihrer Anmeldeinformationen aufgefordert, bevor sie zur Eingabe ihrer PIN aufgefordert werden, ist möglicherweise versehentlich der Registrierungsschlüssel **DisableNTCredentials** auf Clientcomputern konfiguriert (möglicherweise über eine Gruppenrichtlinie).</span><span class="sxs-lookup"><span data-stu-id="9bb5d-156">If users are unintentionally prompted for credentials before they are prompted to enter their PIN, the **DisableNTCredentials** registry key may be unintentionally configured on client computers, possibly through Group Policy.</span></span>
  
<span data-ttu-id="9bb5d-157">Um die zusätzliche Aufforderung zur Eingabe von Anmeldeinformationen zu verhindern, erstellen Sie den folgenden Registrierungseintrag auf der lokalen Arbeitsstation, oder verwenden Sie die administrative Vorlage "Skype for Business", um mithilfe von Gruppenrichtlinien auf alle Benutzer für einen bestimmten Pool zuzutreffen:</span><span class="sxs-lookup"><span data-stu-id="9bb5d-157">To prevent the additional prompt for credentials, create the following registry entry on the local workstation or use the Skype for Business administrative template to apply to all users for a given pool using Group Policy:</span></span>
  
    HKEY_LOCAL_MACHINE\Software\Policies\Microsoft\Office\15.0\Lync
  
    REG_DWORD: DisableNTCredentials
  
    Value: 0x0
  
### <a name="savepassword"></a><span data-ttu-id="9bb5d-158">SavePassword</span><span class="sxs-lookup"><span data-stu-id="9bb5d-158">SavePassword</span></span>

<span data-ttu-id="9bb5d-159">Wenn sich ein Benutzer zum ersten Mal bei Skype for Business anmeldet, wird der Benutzer aufgefordert, sein Kennwort zu speichern.</span><span class="sxs-lookup"><span data-stu-id="9bb5d-159">When a user signs in to Skype for Business for the first time, the user is prompted to save his or her password.</span></span> <span data-ttu-id="9bb5d-160">Wenn diese Option aktiviert ist, kann das Clientzertifikat des Benutzers im persönlichen Zertifikatspeicher und die Windows-Anmeldeinformationen des Benutzers gespeichert werden, die im Anmelde Informations Manager des lokalen Computers gespeichert werden.</span><span class="sxs-lookup"><span data-stu-id="9bb5d-160">If selected, this option allows the user's client certificate to be stored in the personal certificate store and the user's Windows credentials to be stored in the Credential Manager of the local computer.</span></span>
  
<span data-ttu-id="9bb5d-161">Die Registrierungseinstellung **SavePassword** sollte deaktiviert sein, wenn Skype for Business so konfiguriert ist, dass die zweistufige Authentifizierung unterstützt wird.</span><span class="sxs-lookup"><span data-stu-id="9bb5d-161">The **SavePassword** registry setting should be disabled when Skype for Business is configured to support two-factor authentication.</span></span> <span data-ttu-id="9bb5d-162">Wenn Sie verhindern möchten, dass Benutzer ihre Kennwörter speichern, ändern Sie den folgenden Registrierungseintrag auf der lokalen Arbeitsstation, oder verwenden Sie die administrative Vorlage "Skype for Business", um mithilfe von Gruppenrichtlinien auf alle Benutzer für einen bestimmten Pool zuzutreffen:</span><span class="sxs-lookup"><span data-stu-id="9bb5d-162">To prevent users from saving their passwords, change the following registry entry on the local workstation or use the Skype for Business administrative template to apply to all users for a given pool using Group Policy:</span></span>
  
    HKEY_CURRENT_USER\Software\Microsoft\Office\15.0\Lync
  
    REG_DWORD: SavePassword
  
    Value: 0x0
  
## <a name="ad-fs-20-token-replay"></a><span data-ttu-id="9bb5d-163">AD FS 2.0-Tokenwiederholung</span><span class="sxs-lookup"><span data-stu-id="9bb5d-163">AD FS 2.0 Token Replay</span></span>

<span data-ttu-id="9bb5d-p110">AD FS 2.0 stellt eine Funktion bereit, die als Tokenwiederholungserkennung bezeichnet wird und mit welcher mehrere Tokenanforderungen, in denen dasselbe Token verwendet wird, erkannt und verworfen werden können. Ist diese Funktion aktiviert, schützt die Tokenwiederholungserkennung die Integrität von Authentifizierungsanforderungen sowohl im passiven WS-Federation-Profil als auch im SAML WebSSO-Profil, indem sichergestellt wird, dass ein Token nie mehrmals verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="9bb5d-p110">AD FS 2.0 provides a feature referred to as token replay detection, by which multiple token requests using the same token can be detected and then discarded. When this feature is enabled, token replay detection protects the integrity of authentication requests in both the WS-Federation passive profile and the SAML WebSSO profile by making sure that the same token is never used more than once.</span></span>
  
<span data-ttu-id="9bb5d-166">Diese Funktion sollte in Umgebungen aktiviert sein, in denen Sicherheit einen besonders hohen Stellenwert hat, beispielsweise bei der Nutzung von Kiosken.</span><span class="sxs-lookup"><span data-stu-id="9bb5d-166">This feature should be enabled in situations where security is a very high concern such as when using kiosks.</span></span> <span data-ttu-id="9bb5d-167">Weitere Informationen zur Erkennung von Token-Wiedergabe finden Sie unter [bewährte Methoden für die sichere Planung und Bereitstellung von AD FS 2,0](https://go.microsoft.com/fwlink/p/?LinkId=309215).</span><span class="sxs-lookup"><span data-stu-id="9bb5d-167">For more information about token replay detection, see [Best Practices for Secure Planning and Deployment of AD FS 2.0](https://go.microsoft.com/fwlink/p/?LinkId=309215).</span></span>
  
## <a name="external-user-access"></a><span data-ttu-id="9bb5d-168">Zugriff von externen Benutzern</span><span class="sxs-lookup"><span data-stu-id="9bb5d-168">External User Access</span></span>

<span data-ttu-id="9bb5d-169">Die Konfiguration eines ADFS-Proxys oder eines Reverse-Proxys zur Unterstützung der zweistufigen Authentifizierung von Skype for Business in externen Netzwerken wird in diesen Themen nicht behandelt.</span><span class="sxs-lookup"><span data-stu-id="9bb5d-169">Configuring an ADFS Proxy or Reverse Proxy to support Skype for Business two-factor authentication from external networks is not covered in these topics.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="9bb5d-170">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9bb5d-170">See also</span></span>

[<span data-ttu-id="9bb5d-171">Konfigurieren der zweistufigen Authentifizierung in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="9bb5d-171">Configure two-factor authentication in Skype for Business Server</span></span>](configure-two-factor.md)
  
