---
title: 'Lync Server 2013: Planen der zweistufigen Authentifizierung'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Planning for two-factor authentication
ms:assetid: 16f08710-8961-4659-acbf-ebb95a198fb4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn308562(v=OCS.15)
ms:contentKeyID: 54973683
ms.date: 04/06/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b973a1eeb704788eb07e02afc502ac4bbe41544c
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "42139276"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="planning-for-two-factor-authentication-in-lync-server-2013"></a><span data-ttu-id="1fd27-102">Planen der zweistufigen Authentifizierung in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1fd27-102">Planning for two-factor authentication in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1fd27-103">_**Letztes Änderungsstand des Themas:** 2015-04-06_</span><span class="sxs-lookup"><span data-stu-id="1fd27-103">_**Topic Last Modified:** 2015-04-06_</span></span>

<span data-ttu-id="1fd27-104">Im folgenden finden Sie eine Liste der Bereitstellungsüberlegungen beim Konfigurieren einer Microsoft lync Server 2013 Umgebung zur Unterstützung der zweistufigen Authentifizierung.</span><span class="sxs-lookup"><span data-stu-id="1fd27-104">The following is a list of deployment considerations when configuring a Microsoft Lync Server 2013 environment to support two-factor authentication.</span></span>

<div>

## <a name="client-support"></a><span data-ttu-id="1fd27-105">Client Unterstützung</span><span class="sxs-lookup"><span data-stu-id="1fd27-105">Client Support</span></span>

<span data-ttu-id="1fd27-106">Die lync 2013 kumulativen Updates für lync Server 2013: July 2013 Desktop Client und alle mobilen Clients unterstützen derzeit die zweistufige Authentifizierung.</span><span class="sxs-lookup"><span data-stu-id="1fd27-106">The Lync 2013 Cumulative Updates for Lync Server 2013: July 2013 desktop client and all mobile clients currently support two-factor authentication.</span></span>

</div>

<div>

## <a name="topology-requirements"></a><span data-ttu-id="1fd27-107">Anforderungen im Hinblick auf die Topologie</span><span class="sxs-lookup"><span data-stu-id="1fd27-107">Topology Requirements</span></span>

<span data-ttu-id="1fd27-108">Kunden wird dringend empfohlen, die zweistufige Authentifizierung mithilfe dedizierter lync Server 2013 mit kumulierten Updates für lync Server 2013 bereitzustellen: July 2013 Edge, Director und User Pools.</span><span class="sxs-lookup"><span data-stu-id="1fd27-108">Customers are strongly encouraged to deploy two-factor authentication using dedicated Lync Server 2013 with Cumulative Updates for Lync Server 2013: July 2013 Edge, Director, and User Pools.</span></span> <span data-ttu-id="1fd27-109">Zum Aktivieren der passiven Authentifizierung für lync-Benutzer müssen andere Authentifizierungsmethoden für andere Rollen und Dienste deaktiviert sein, einschließlich der folgenden:</span><span class="sxs-lookup"><span data-stu-id="1fd27-109">To enable passive authentication for Lync users, other authentication methods must be disabled for other roles and services, including the following:</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="1fd27-110">Konfigurationstyp</span><span class="sxs-lookup"><span data-stu-id="1fd27-110">Configuration Type</span></span></th>
<th><span data-ttu-id="1fd27-111">Diensttyp</span><span class="sxs-lookup"><span data-stu-id="1fd27-111">Service Type</span></span></th>
<th><span data-ttu-id="1fd27-112">Serverrolle</span><span class="sxs-lookup"><span data-stu-id="1fd27-112">Server Role</span></span></th>
<th><span data-ttu-id="1fd27-113">Zu deaktivierender Authentifizierungstyp</span><span class="sxs-lookup"><span data-stu-id="1fd27-113">Authentication Type to Disable</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="1fd27-114">Webdienst</span><span class="sxs-lookup"><span data-stu-id="1fd27-114">Web Service</span></span></p></td>
<td><p><span data-ttu-id="1fd27-115">Webserver</span><span class="sxs-lookup"><span data-stu-id="1fd27-115">WebServer</span></span></p></td>
<td><p><span data-ttu-id="1fd27-116">Director</span><span class="sxs-lookup"><span data-stu-id="1fd27-116">Director</span></span></p></td>
<td><p><span data-ttu-id="1fd27-117">Kerberos, NTLM und Zertifikat</span><span class="sxs-lookup"><span data-stu-id="1fd27-117">Kerberos, NTLM, and Certificate</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1fd27-118">Webdienst</span><span class="sxs-lookup"><span data-stu-id="1fd27-118">Web Service</span></span></p></td>
<td><p><span data-ttu-id="1fd27-119">Webserver</span><span class="sxs-lookup"><span data-stu-id="1fd27-119">WebServer</span></span></p></td>
<td><p><span data-ttu-id="1fd27-120">Front-End-</span><span class="sxs-lookup"><span data-stu-id="1fd27-120">Front End</span></span></p></td>
<td><p><span data-ttu-id="1fd27-121">Kerberos, NTLM und Zertifikat</span><span class="sxs-lookup"><span data-stu-id="1fd27-121">Kerberos, NTLM, and Certificate</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1fd27-122">Proxy</span><span class="sxs-lookup"><span data-stu-id="1fd27-122">Proxy</span></span></p></td>
<td><p><span data-ttu-id="1fd27-123">EdgeServer</span><span class="sxs-lookup"><span data-stu-id="1fd27-123">EdgeServer</span></span></p></td>
<td><p><span data-ttu-id="1fd27-124">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="1fd27-124">Edge</span></span></p></td>
<td><p><span data-ttu-id="1fd27-125">Kerberos und NTLM</span><span class="sxs-lookup"><span data-stu-id="1fd27-125">Kerberos and NTLM</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1fd27-126">Proxy</span><span class="sxs-lookup"><span data-stu-id="1fd27-126">Proxy</span></span></p></td>
<td><p><span data-ttu-id="1fd27-127">Registrierungsstelle</span><span class="sxs-lookup"><span data-stu-id="1fd27-127">Registrar</span></span></p></td>
<td><p><span data-ttu-id="1fd27-128">Front-End-</span><span class="sxs-lookup"><span data-stu-id="1fd27-128">Front End</span></span></p></td>
<td><p><span data-ttu-id="1fd27-129">Kerberos und NTLM</span><span class="sxs-lookup"><span data-stu-id="1fd27-129">Kerberos and NTLM</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="1fd27-130">Wenn diese Authentifizierungstypen auf Dienstebene deaktiviert sind, können sich alle anderen Versionen des lync-Clients nicht erfolgreich anmelden, wenn die zweistufige Authentifizierung in Ihrer Bereitstellung aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="1fd27-130">Unless these authentication types are disabled at the service level, all other versions of the Lync client will be unable to sign in successfully once two-factor authentication is enabled within in your deployment.</span></span>

</div>

<div>

## <a name="lync-service-discovery"></a><span data-ttu-id="1fd27-131">Lync-Dienstermittlung</span><span class="sxs-lookup"><span data-stu-id="1fd27-131">Lync Service Discovery</span></span>

<span data-ttu-id="1fd27-132">DNS-Einträge, die von internen und/oder externen Clients zum Ermitteln von lync-Diensten verwendet werden, sollten so konfiguriert werden, dass Sie auf einen lync-Server aufgelöst werden, der nicht für die zweistufige Authentifizierung aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="1fd27-132">DNS records used by internal and/or external clients to discover Lync services should be configured to resolve to a Lync server that is not enabled for two-factor authentication.</span></span> <span data-ttu-id="1fd27-133">Bei dieser Konfiguration müssen Benutzer aus lync-Pools, die nicht für die zweistufige Authentifizierung aktiviert sind, keine PIN zur Authentifizierung eingeben, während Benutzer aus lync-Pools, die für die zweistufige Authentifizierung aktiviert sind, Ihre PIN eingeben müssen, um authentifizieren.</span><span class="sxs-lookup"><span data-stu-id="1fd27-133">With this configuration, users from Lync Pools that are not enabled for two-factor authentication will not be required to enter a PIN to authenticate, while users from Lync Pools that are enabled for two-factor authentication will be required to enter their PIN to authenticate.</span></span>

</div>

<div>

## <a name="exchange-authentication"></a><span data-ttu-id="1fd27-134">Exchange-Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="1fd27-134">Exchange Authentication</span></span>

<span data-ttu-id="1fd27-135">Kunden, die die zweistufige Authentifizierung für Microsoft Exchange bereitgestellt haben, stellen möglicherweise fest, dass bestimmte Funktionen im lync-Client nicht verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="1fd27-135">Customers who have deployed two-factor authentication for Microsoft Exchange may find that certain features in the Lync client are unavailable.</span></span> <span data-ttu-id="1fd27-136">Dies ist derzeit beabsichtigt, da der lync-Client die zweistufige Authentifizierung nicht für Features unterstützt, die von der Exchange-Integration abhängen.</span><span class="sxs-lookup"><span data-stu-id="1fd27-136">This is currently by design, as the Lync client does not support two-factor authentication for features that are dependent on Exchange integration.</span></span>

</div>

<div>

## <a name="lync-contacts"></a><span data-ttu-id="1fd27-137">Lync-Kontakte</span><span class="sxs-lookup"><span data-stu-id="1fd27-137">Lync Contacts</span></span>

<span data-ttu-id="1fd27-138">Lync-Benutzer, die für die Nutzung der Unified Contact Store-Funktion konfiguriert sind, werden feststellen, dass Ihre Kontakte nach der Anmeldung mit zweistufiger Authentifizierung nicht mehr verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="1fd27-138">Lync users who are configured to leverage the Unified Contact Store feature will find that their contacts are no longer available after signing in with two-factor authentication.</span></span>

<span data-ttu-id="1fd27-139">Verwenden Sie das Cmdlet **Invoke-CsUcsRollback** , um vorhandene Benutzer Kontakte aus dem einheitlichen Kontaktspeicher zu entfernen und in lync Server 2013 zu speichern, bevor Sie die zweistufige Authentifizierung aktivieren.</span><span class="sxs-lookup"><span data-stu-id="1fd27-139">You should use the **Invoke-CsUcsRollback** cmdlet to remove existing user contacts from the Unified Contact Store and store them in Lync Server 2013 before enabling two-factor authentication.</span></span>

</div>

<div>

## <a name="skill-search"></a><span data-ttu-id="1fd27-140">Skill-Suche</span><span class="sxs-lookup"><span data-stu-id="1fd27-140">Skill Search</span></span>

<span data-ttu-id="1fd27-141">Kunden, die das Feature "Fähigkeitssuche" in ihrer lync-Umgebung konfiguriert haben, werden feststellen, dass dieses Feature nicht funktioniert, wenn lync für die zweistufige Authentifizierung aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="1fd27-141">Customers who have configured the Skill Search feature in their Lync environment will find that this feature does not work when Lync is enabled for two-factor authentication.</span></span> <span data-ttu-id="1fd27-142">Dies ist beabsichtigt, da Microsoft SharePoint derzeit keine zweistufige Authentifizierung unterstützt.</span><span class="sxs-lookup"><span data-stu-id="1fd27-142">This is by design, as Microsoft SharePoint does not currently support two-factor authentication.</span></span>

</div>

<div>

## <a name="lync-credentials"></a><span data-ttu-id="1fd27-143">Lync-Anmeldeinformationen</span><span class="sxs-lookup"><span data-stu-id="1fd27-143">Lync Credentials</span></span>

<span data-ttu-id="1fd27-144">Es gibt eine Reihe von Überlegungen zur Bereitstellung von gespeicherten lync-Anmeldeinformationen, die sich auf Benutzer auswirken können, die für die Verwendung der zweistufigen Authentifizierung konfiguriert sind.</span><span class="sxs-lookup"><span data-stu-id="1fd27-144">There are a number of deployment considerations involving saved Lync credentials which may impact users who are configured to use two-factor authentication.</span></span>

<div>

## <a name="deleting-saved-credentials"></a><span data-ttu-id="1fd27-145">Löschen gespeicherter Anmeldeinformationen</span><span class="sxs-lookup"><span data-stu-id="1fd27-145">Deleting Saved Credentials</span></span>

<span data-ttu-id="1fd27-146">Benutzer von Desktop Clients sollten die **Option Meine Anmeldeinformationen löschen** im lync-Client verwenden und Ihren SIP-Profilordner aus% LocalAppData%\\Microsoft\\Office\\15,0\\lync löschen, bevor Sie versuchen, das erste Mal unter Verwendung der zweistufigen Authentifizierung zu signieren.</span><span class="sxs-lookup"><span data-stu-id="1fd27-146">Desktop client users should use the **Delete my sign-in info** option in the Lync client and delete their SIP profile folder from %localappdata%\\Microsoft\\Office\\15.0\\Lync before attempting to sign for the first time using two-factor authentication.</span></span>

</div>

<div>

## <a name="disablentcredentials"></a><span data-ttu-id="1fd27-147">DisableNTCredentials</span><span class="sxs-lookup"><span data-stu-id="1fd27-147">DisableNTCredentials</span></span>

<span data-ttu-id="1fd27-148">Bei der Kerberos-oder NTLM-Authentifizierungsmethode werden die Windows-Anmeldeinformationen des Benutzers automatisch für die Authentifizierung verwendet.</span><span class="sxs-lookup"><span data-stu-id="1fd27-148">With the Kerberos or NTLM authentication method, the user’s Windows credentials are used automatically for authentication.</span></span> <span data-ttu-id="1fd27-149">In einer typischen lync Server 2013-Bereitstellung, bei der Kerberos und/oder NTLM für die Authentifizierung aktiviert ist, sollten Benutzer nicht jedes Mal, wenn Sie sich anmelden, Ihre Anmeldeinformationen eingeben müssen.</span><span class="sxs-lookup"><span data-stu-id="1fd27-149">In a typical Lync Server 2013 deployment where Kerberos and/or NTLM is enabled for authentication, users should not have to enter their credentials every time that they sign in.</span></span>

<span data-ttu-id="1fd27-150">Wenn Benutzer versehentlich zur Eingabe von Anmeldeinformationen aufgefordert werden, bevor Sie dazu aufgefordert werden, Ihre PIN einzugeben, kann der Registrierungsschlüssel **DisableNTCredentials** möglicherweise über eine Gruppenrichtlinie unbeabsichtigt auf Clientcomputern konfiguriert werden.</span><span class="sxs-lookup"><span data-stu-id="1fd27-150">If users are unintentionally prompted for credentials before they are prompted to enter their PIN, the **DisableNTCredentials** registry key may be unintentionally configured on client computers, possibly through Group Policy.</span></span>

<span data-ttu-id="1fd27-151">Um die zusätzliche Aufforderung zur Eingabe von Anmeldeinformationen zu verhindern, erstellen Sie den folgenden Registrierungseintrag auf der lokalen Arbeitsstation, oder verwenden Sie die administrative Vorlage lync, um mithilfe von Gruppenrichtlinien auf alle Benutzer für einen bestimmten Pool zuzutreffen:</span><span class="sxs-lookup"><span data-stu-id="1fd27-151">To prevent the additional prompt for credentials, create the following registry entry on the local workstation or use the Lync administrative template to apply to all users for a given pool using Group Policy:</span></span>

<span data-ttu-id="1fd27-152">HKEY\_-\_Software\\\\Richtlinien\\für lokale\\Computer\\Microsoft\\Office 15,0 lync</span><span class="sxs-lookup"><span data-stu-id="1fd27-152">HKEY\_LOCAL\_MACHINE\\Software\\Policies\\Microsoft\\Office\\15.0\\Lync</span></span>

<span data-ttu-id="1fd27-153">REG\_DWORD: DisableNTCredentials</span><span class="sxs-lookup"><span data-stu-id="1fd27-153">REG\_DWORD: DisableNTCredentials</span></span>

<span data-ttu-id="1fd27-154">Wert: 0x0 festlegen</span><span class="sxs-lookup"><span data-stu-id="1fd27-154">Value: 0x0</span></span>

</div>

<div>

## <a name="savepassword"></a><span data-ttu-id="1fd27-155">SavePassword</span><span class="sxs-lookup"><span data-stu-id="1fd27-155">SavePassword</span></span>

<span data-ttu-id="1fd27-156">Wenn sich ein Benutzer zum ersten Mal bei lync anmeldet, wird der Benutzer aufgefordert, sein Kennwort zu speichern.</span><span class="sxs-lookup"><span data-stu-id="1fd27-156">When a user signs in to Lync for the first time, the user is prompted to save his or her password.</span></span> <span data-ttu-id="1fd27-157">Wenn diese Option aktiviert ist, kann das Clientzertifikat des Benutzers im persönlichen Zertifikatspeicher und in den Windows-Anmeldeinformationen des Benutzers gespeichert werden, damit diese im Credential Manager des lokalen Computers gespeichert werden.</span><span class="sxs-lookup"><span data-stu-id="1fd27-157">If selected, this option allows the user’s client certificate to be stored in the personal certificate store and the user’s Windows credentials to be stored in the Credential Manager of the local computer.</span></span>

<span data-ttu-id="1fd27-158">Die Registrierungseinstellung **SavePassword** sollte deaktiviert werden, wenn lync für die Unterstützung der zweistufigen Authentifizierung konfiguriert ist.</span><span class="sxs-lookup"><span data-stu-id="1fd27-158">The **SavePassword** registry setting should be disabled when Lync is configured to support two-factor authentication.</span></span> <span data-ttu-id="1fd27-159">Wenn Sie verhindern möchten, dass Benutzer ihre Kennwörter speichern, ändern Sie den folgenden Registrierungseintrag auf der lokalen Arbeitsstation, oder verwenden Sie die administrative Vorlage lync, um mithilfe von Gruppenrichtlinien auf alle Benutzer für einen bestimmten Pool zuzutreffen:</span><span class="sxs-lookup"><span data-stu-id="1fd27-159">To prevent users from saving their passwords, change the following registry entry on the local workstation or use the Lync administrative template to apply to all users for a given pool using Group Policy:</span></span>

<span data-ttu-id="1fd27-160">HKEY\_aktuelle\_Benutzer\\Software\\Microsoft\\Office\\15,0\\lync</span><span class="sxs-lookup"><span data-stu-id="1fd27-160">HKEY\_CURRENT\_USER\\Software\\Microsoft\\Office\\15.0\\Lync</span></span>

<span data-ttu-id="1fd27-161">REG\_DWORD: SavePassword</span><span class="sxs-lookup"><span data-stu-id="1fd27-161">REG\_DWORD: SavePassword</span></span>

<span data-ttu-id="1fd27-162">Wert: 0x0 festlegen</span><span class="sxs-lookup"><span data-stu-id="1fd27-162">Value: 0x0</span></span>

</div>

</div>

<div>

## <a name="ad-fs-20-token-replay"></a><span data-ttu-id="1fd27-163">Wiedergabe von AD FS 2.0 Token</span><span class="sxs-lookup"><span data-stu-id="1fd27-163">AD FS 2.0 Token Replay</span></span>

<span data-ttu-id="1fd27-164">AD FS 2.0 stellt ein Feature dar, das als Erkennung von Token-Wiedergaben bezeichnet wird, durch das mehrere Token-Anforderungen mit demselben Token erkannt und anschließend verworfen werden können.</span><span class="sxs-lookup"><span data-stu-id="1fd27-164">AD FS 2.0 provides a feature referred to as token replay detection, by which multiple token requests using the same token can be detected and then discarded.</span></span> <span data-ttu-id="1fd27-165">Wenn dieses Feature aktiviert ist, schützt die Token-Wiedergabeerkennung die Integrität von Authentifizierungsanforderungen sowohl im passiven WS-verbundprofil als auch im SAML-WebSSO-Profil, indem sichergestellt wird, dass das gleiche Token nie mehr als einmal verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="1fd27-165">When this feature is enabled, token replay detection protects the integrity of authentication requests in both the WS-Federation passive profile and the SAML WebSSO profile by making sure that the same token is never used more than once.</span></span>

<span data-ttu-id="1fd27-166">Dieses Feature sollte in Situationen aktiviert sein, in denen Sicherheit ein sehr hoher Aspekt ist, beispielsweise bei der Verwendung von Kiosken.</span><span class="sxs-lookup"><span data-stu-id="1fd27-166">This feature should be enabled in situations where security is a very high concern such as when using kiosks.</span></span> <span data-ttu-id="1fd27-167">Weitere Informationen zur Erkennung von Token-Wiedergabe finden Sie unter Bewährte Methoden für die sichere Planung und bereit [https://go.microsoft.com/fwlink/p/?LinkId=309215](https://go.microsoft.com/fwlink/p/?linkid=309215)Stellung von AD FS 2.0 unter.</span><span class="sxs-lookup"><span data-stu-id="1fd27-167">For more information about token replay detection, see Best Practices for Secure Planning and Deployment of AD FS 2.0 at [https://go.microsoft.com/fwlink/p/?LinkId=309215](https://go.microsoft.com/fwlink/p/?linkid=309215).</span></span>

</div>

<div>

## <a name="external-user-access"></a><span data-ttu-id="1fd27-168">Externer Benutzerzugriff</span><span class="sxs-lookup"><span data-stu-id="1fd27-168">External User Access</span></span>

<span data-ttu-id="1fd27-169">Die Konfiguration eines AD FS-Proxys oder Reverseproxy zur Unterstützung der zweistufigen lync-Authentifizierung von externen Netzwerken wird in diesen Themen nicht behandelt.</span><span class="sxs-lookup"><span data-stu-id="1fd27-169">Configuring an AD FS Proxy or Reverse Proxy to support Lync two-factor authentication from external networks is not covered in these topics.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

