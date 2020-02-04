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
ms.openlocfilehash: e610990182e01c0e9e2d7199bd3a34f70fbe3132
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41750435"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="planning-for-two-factor-authentication-in-lync-server-2013"></a><span data-ttu-id="35f2c-102">Planen der zweistufigen Authentifizierung in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="35f2c-102">Planning for two-factor authentication in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="35f2c-103">_**Letztes Änderungsdatum des Themas:** 2015-04-06_</span><span class="sxs-lookup"><span data-stu-id="35f2c-103">_**Topic Last Modified:** 2015-04-06_</span></span>

<span data-ttu-id="35f2c-104">Im folgenden wird eine Liste der Bereitstellungsüberlegungen beim Konfigurieren einer Microsoft lync Server 2013-Umgebung zur Unterstützung der zweistufigen Authentifizierung aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="35f2c-104">The following is a list of deployment considerations when configuring a Microsoft Lync Server 2013 environment to support two-factor authentication.</span></span>

<div>

## <a name="client-support"></a><span data-ttu-id="35f2c-105">Clientunterstützung</span><span class="sxs-lookup"><span data-stu-id="35f2c-105">Client Support</span></span>

<span data-ttu-id="35f2c-106">Die lync 2013-kumulativen Updates für lync Server 2013: Juli 2013-Desktop Client und alle mobilen Clients unterstützen derzeit die zweistufige Authentifizierung.</span><span class="sxs-lookup"><span data-stu-id="35f2c-106">The Lync 2013 Cumulative Updates for Lync Server 2013: July 2013 desktop client and all mobile clients currently support two-factor authentication.</span></span>

</div>

<div>

## <a name="topology-requirements"></a><span data-ttu-id="35f2c-107">Anforderungen im Hinblick auf die Topologie</span><span class="sxs-lookup"><span data-stu-id="35f2c-107">Topology Requirements</span></span>

<span data-ttu-id="35f2c-108">Kunden werden dringend ermutigt, die zweistufige Authentifizierung mit dedizierten lync Server 2013 mit kumulativen Updates für lync Server 2013: Juli 2013 Edge-, Director-und Benutzer Pools bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="35f2c-108">Customers are strongly encouraged to deploy two-factor authentication using dedicated Lync Server 2013 with Cumulative Updates for Lync Server 2013: July 2013 Edge, Director, and User Pools.</span></span> <span data-ttu-id="35f2c-109">Um die passive Authentifizierung für lync-Benutzer zu aktivieren, müssen andere Authentifizierungsmethoden für andere Rollen und Dienste deaktiviert sein, einschließlich der folgenden:</span><span class="sxs-lookup"><span data-stu-id="35f2c-109">To enable passive authentication for Lync users, other authentication methods must be disabled for other roles and services, including the following:</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="35f2c-110">Konfigurationstyp</span><span class="sxs-lookup"><span data-stu-id="35f2c-110">Configuration Type</span></span></th>
<th><span data-ttu-id="35f2c-111">Diensttyp</span><span class="sxs-lookup"><span data-stu-id="35f2c-111">Service Type</span></span></th>
<th><span data-ttu-id="35f2c-112">Serverrolle</span><span class="sxs-lookup"><span data-stu-id="35f2c-112">Server Role</span></span></th>
<th><span data-ttu-id="35f2c-113">Zu deaktivierender Authentifizierungstyp</span><span class="sxs-lookup"><span data-stu-id="35f2c-113">Authentication Type to Disable</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="35f2c-114">Webdienst</span><span class="sxs-lookup"><span data-stu-id="35f2c-114">Web Service</span></span></p></td>
<td><p><span data-ttu-id="35f2c-115">WebServer</span><span class="sxs-lookup"><span data-stu-id="35f2c-115">WebServer</span></span></p></td>
<td><p><span data-ttu-id="35f2c-116">Director</span><span class="sxs-lookup"><span data-stu-id="35f2c-116">Director</span></span></p></td>
<td><p><span data-ttu-id="35f2c-117">Kerberos, NTLM und Zertifikat</span><span class="sxs-lookup"><span data-stu-id="35f2c-117">Kerberos, NTLM, and Certificate</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="35f2c-118">Webdienst</span><span class="sxs-lookup"><span data-stu-id="35f2c-118">Web Service</span></span></p></td>
<td><p><span data-ttu-id="35f2c-119">WebServer</span><span class="sxs-lookup"><span data-stu-id="35f2c-119">WebServer</span></span></p></td>
<td><p><span data-ttu-id="35f2c-120">Front-End</span><span class="sxs-lookup"><span data-stu-id="35f2c-120">Front End</span></span></p></td>
<td><p><span data-ttu-id="35f2c-121">Kerberos, NTLM und Zertifikat</span><span class="sxs-lookup"><span data-stu-id="35f2c-121">Kerberos, NTLM, and Certificate</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="35f2c-122">Proxy</span><span class="sxs-lookup"><span data-stu-id="35f2c-122">Proxy</span></span></p></td>
<td><p><span data-ttu-id="35f2c-123">EdgeServer</span><span class="sxs-lookup"><span data-stu-id="35f2c-123">EdgeServer</span></span></p></td>
<td><p><span data-ttu-id="35f2c-124">Edge</span><span class="sxs-lookup"><span data-stu-id="35f2c-124">Edge</span></span></p></td>
<td><p><span data-ttu-id="35f2c-125">Kerberos und NTLM</span><span class="sxs-lookup"><span data-stu-id="35f2c-125">Kerberos and NTLM</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="35f2c-126">Proxy</span><span class="sxs-lookup"><span data-stu-id="35f2c-126">Proxy</span></span></p></td>
<td><p><span data-ttu-id="35f2c-127">Registrierungsstelle</span><span class="sxs-lookup"><span data-stu-id="35f2c-127">Registrar</span></span></p></td>
<td><p><span data-ttu-id="35f2c-128">Front-End</span><span class="sxs-lookup"><span data-stu-id="35f2c-128">Front End</span></span></p></td>
<td><p><span data-ttu-id="35f2c-129">Kerberos und NTLM</span><span class="sxs-lookup"><span data-stu-id="35f2c-129">Kerberos and NTLM</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="35f2c-130">Sofern diese Authentifizierungstypen nicht auf Dienstebene deaktiviert sind, können sich alle anderen Versionen des lync-Clients nicht erfolgreich anmelden, wenn die zweistufige Authentifizierung innerhalb Ihrer Bereitstellung aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="35f2c-130">Unless these authentication types are disabled at the service level, all other versions of the Lync client will be unable to sign in successfully once two-factor authentication is enabled within in your deployment.</span></span>

</div>

<div>

## <a name="lync-service-discovery"></a><span data-ttu-id="35f2c-131">Lync-Dienstermittlung</span><span class="sxs-lookup"><span data-stu-id="35f2c-131">Lync Service Discovery</span></span>

<span data-ttu-id="35f2c-132">DNS-Einträge, die von internen und/oder externen Clients zum Ermitteln von lync-Diensten verwendet werden, sollten so konfiguriert werden, dass Sie auf einen lync-Server aufgelöst werden, der für die zweistufige Authentifizierung nicht aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="35f2c-132">DNS records used by internal and/or external clients to discover Lync services should be configured to resolve to a Lync server that is not enabled for two-factor authentication.</span></span> <span data-ttu-id="35f2c-133">Bei dieser Konfiguration müssen Benutzer aus lync-Pools, die nicht für die zweistufige Authentifizierung aktiviert sind, keine PIN zur Authentifizierung eingeben, während Benutzer aus lync-Pools, die für die zweistufige Authentifizierung aktiviert sind, Ihre PIN eingeben müssen, um authentifizieren.</span><span class="sxs-lookup"><span data-stu-id="35f2c-133">With this configuration, users from Lync Pools that are not enabled for two-factor authentication will not be required to enter a PIN to authenticate, while users from Lync Pools that are enabled for two-factor authentication will be required to enter their PIN to authenticate.</span></span>

</div>

<div>

## <a name="exchange-authentication"></a><span data-ttu-id="35f2c-134">Exchange-Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="35f2c-134">Exchange Authentication</span></span>

<span data-ttu-id="35f2c-135">Kunden, die die zweistufige Authentifizierung für Microsoft Exchange bereitgestellt haben, können feststellen, dass bestimmte Features im lync-Client nicht verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="35f2c-135">Customers who have deployed two-factor authentication for Microsoft Exchange may find that certain features in the Lync client are unavailable.</span></span> <span data-ttu-id="35f2c-136">Dies ist derzeit beabsichtigt, da der lync-Client die zweistufige Authentifizierung für Features, die von der Exchange-Integration abhängig sind, nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="35f2c-136">This is currently by design, as the Lync client does not support two-factor authentication for features that are dependent on Exchange integration.</span></span>

</div>

<div>

## <a name="lync-contacts"></a><span data-ttu-id="35f2c-137">Lync-Kontakte</span><span class="sxs-lookup"><span data-stu-id="35f2c-137">Lync Contacts</span></span>

<span data-ttu-id="35f2c-138">Lync-Benutzer, die für die Nutzung des Unified Contact Store-Features konfiguriert sind, werden feststellen, dass Ihre Kontakte nach der Anmeldung mit zweistufiger Authentifizierung nicht mehr verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="35f2c-138">Lync users who are configured to leverage the Unified Contact Store feature will find that their contacts are no longer available after signing in with two-factor authentication.</span></span>

<span data-ttu-id="35f2c-139">Sie sollten das Cmdlet **Invoke-CsUcsRollback** verwenden, um vorhandene Benutzer Kontakte aus dem Unified Contact Store zu entfernen und in lync Server 2013 zu speichern, bevor Sie die zweistufige Authentifizierung aktivieren.</span><span class="sxs-lookup"><span data-stu-id="35f2c-139">You should use the **Invoke-CsUcsRollback** cmdlet to remove existing user contacts from the Unified Contact Store and store them in Lync Server 2013 before enabling two-factor authentication.</span></span>

</div>

<div>

## <a name="skill-search"></a><span data-ttu-id="35f2c-140">Qualifikationssuche</span><span class="sxs-lookup"><span data-stu-id="35f2c-140">Skill Search</span></span>

<span data-ttu-id="35f2c-141">Kunden, die das Feature für die Fertigkeits Suche in ihrer lync-Umgebung konfiguriert haben, werden feststellen, dass dieses Feature nicht funktioniert, wenn lync für die zweistufige Authentifizierung aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="35f2c-141">Customers who have configured the Skill Search feature in their Lync environment will find that this feature does not work when Lync is enabled for two-factor authentication.</span></span> <span data-ttu-id="35f2c-142">Dies ist entwurfsbedingt, weil Microsoft SharePoint momentan die zweistufige Authentifizierung nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="35f2c-142">This is by design, as Microsoft SharePoint does not currently support two-factor authentication.</span></span>

</div>

<div>

## <a name="lync-credentials"></a><span data-ttu-id="35f2c-143">Lync-Anmeldeinformationen</span><span class="sxs-lookup"><span data-stu-id="35f2c-143">Lync Credentials</span></span>

<span data-ttu-id="35f2c-144">Es gibt eine Reihe von Bereitstellungsüberlegungen mit gespeicherten lync-Anmeldeinformationen, die sich auf Benutzer auswirken können, die für die Verwendung der zweistufigen Authentifizierung konfiguriert sind.</span><span class="sxs-lookup"><span data-stu-id="35f2c-144">There are a number of deployment considerations involving saved Lync credentials which may impact users who are configured to use two-factor authentication.</span></span>

<div>

## <a name="deleting-saved-credentials"></a><span data-ttu-id="35f2c-145">Löschen von gespeicherten Anmeldeinformationen</span><span class="sxs-lookup"><span data-stu-id="35f2c-145">Deleting Saved Credentials</span></span>

<span data-ttu-id="35f2c-146">Desktop Clientbenutzer sollten die Option **Meine Anmeldeinformationen löschen** im lync-Client verwenden und Ihren SIP-Profilordner von% LocalAppData\\% Microsoft\\Office\\15,0\\lync löschen, bevor Sie versuchen, das erste Mal mithilfe der zweistufigen Authentifizierung zu signieren.</span><span class="sxs-lookup"><span data-stu-id="35f2c-146">Desktop client users should use the **Delete my sign-in info** option in the Lync client and delete their SIP profile folder from %localappdata%\\Microsoft\\Office\\15.0\\Lync before attempting to sign for the first time using two-factor authentication.</span></span>

</div>

<div>

## <a name="disablentcredentials"></a><span data-ttu-id="35f2c-147">DisableNTCredentials</span><span class="sxs-lookup"><span data-stu-id="35f2c-147">DisableNTCredentials</span></span>

<span data-ttu-id="35f2c-148">Im Rahmen der Kerberos- oder NTLM-Authentifizierungsmethode werden die Windows-Anmeldeinformationen des Benutzers automatisch für die Authentifizierung verwendet.</span><span class="sxs-lookup"><span data-stu-id="35f2c-148">With the Kerberos or NTLM authentication method, the user’s Windows credentials are used automatically for authentication.</span></span> <span data-ttu-id="35f2c-149">In einer typischen lync Server 2013-Bereitstellung, bei der Kerberos und/oder NTLM für die Authentifizierung aktiviert ist, sollten Benutzer nicht bei jeder Anmeldung Ihre Anmeldeinformationen eingeben müssen.</span><span class="sxs-lookup"><span data-stu-id="35f2c-149">In a typical Lync Server 2013 deployment where Kerberos and/or NTLM is enabled for authentication, users should not have to enter their credentials every time that they sign in.</span></span>

<span data-ttu-id="35f2c-150">Werden Benutzer unbeabsichtigt zur Eingabe ihrer Anmeldeinformationen aufgefordert, bevor sie zur Eingabe ihrer PIN aufgefordert werden, ist möglicherweise versehentlich der Registrierungsschlüssel **DisableNTCredentials** auf Clientcomputern konfiguriert (möglicherweise über eine Gruppenrichtlinie).</span><span class="sxs-lookup"><span data-stu-id="35f2c-150">If users are unintentionally prompted for credentials before they are prompted to enter their PIN, the **DisableNTCredentials** registry key may be unintentionally configured on client computers, possibly through Group Policy.</span></span>

<span data-ttu-id="35f2c-151">Um die zusätzliche Aufforderung zur Eingabe von Anmeldeinformationen zu verhindern, erstellen Sie den folgenden Registrierungseintrag auf der lokalen Arbeitsstation, oder verwenden Sie die administrative lync-Vorlage, um auf alle Benutzer für einen bestimmten Pool über Gruppenrichtlinien zuzutreffen:</span><span class="sxs-lookup"><span data-stu-id="35f2c-151">To prevent the additional prompt for credentials, create the following registry entry on the local workstation or use the Lync administrative template to apply to all users for a given pool using Group Policy:</span></span>

<span data-ttu-id="35f2c-152">HKEY\_-\_Software\\\\Richtlinien\\für lokale\\Computer\\Microsoft\\Office 15,0 lync</span><span class="sxs-lookup"><span data-stu-id="35f2c-152">HKEY\_LOCAL\_MACHINE\\Software\\Policies\\Microsoft\\Office\\15.0\\Lync</span></span>

<span data-ttu-id="35f2c-153">REG\_DWORD: DisableNTCredentials</span><span class="sxs-lookup"><span data-stu-id="35f2c-153">REG\_DWORD: DisableNTCredentials</span></span>

<span data-ttu-id="35f2c-154">Wert: 0x0</span><span class="sxs-lookup"><span data-stu-id="35f2c-154">Value: 0x0</span></span>

</div>

<div>

## <a name="savepassword"></a><span data-ttu-id="35f2c-155">SavePassword</span><span class="sxs-lookup"><span data-stu-id="35f2c-155">SavePassword</span></span>

<span data-ttu-id="35f2c-156">Wenn sich ein Benutzer zum ersten Mal bei lync anmeldet, wird der Benutzer aufgefordert, sein Kennwort zu speichern.</span><span class="sxs-lookup"><span data-stu-id="35f2c-156">When a user signs in to Lync for the first time, the user is prompted to save his or her password.</span></span> <span data-ttu-id="35f2c-157">Wird diese Option ausgewählt, ermöglicht sie es, dass das Clientzertifikat des Benutzers im persönlichen Zertifikatspeicher und die Windows-Anmeldeinformationen des Benutzers in der Anmeldeinformationsverwaltung auf dem lokalen Computer gespeichert werden.</span><span class="sxs-lookup"><span data-stu-id="35f2c-157">If selected, this option allows the user’s client certificate to be stored in the personal certificate store and the user’s Windows credentials to be stored in the Credential Manager of the local computer.</span></span>

<span data-ttu-id="35f2c-158">Die Registrierungseinstellung **SavePassword** sollte deaktiviert werden, wenn lync so konfiguriert ist, dass die zweistufige Authentifizierung unterstützt wird.</span><span class="sxs-lookup"><span data-stu-id="35f2c-158">The **SavePassword** registry setting should be disabled when Lync is configured to support two-factor authentication.</span></span> <span data-ttu-id="35f2c-159">Wenn Sie verhindern möchten, dass Benutzer ihre Kennwörter speichern, ändern Sie den folgenden Registrierungseintrag auf der lokalen Arbeitsstation, oder verwenden Sie die administrative lync-Vorlage, um mithilfe von Gruppenrichtlinien auf alle Benutzer für einen bestimmten Pool zuzutreffen:</span><span class="sxs-lookup"><span data-stu-id="35f2c-159">To prevent users from saving their passwords, change the following registry entry on the local workstation or use the Lync administrative template to apply to all users for a given pool using Group Policy:</span></span>

<span data-ttu-id="35f2c-160">HKEY\_-\_aktuelle\\Benutzer\\Software\\Microsoft\\Office\\15,0 lync</span><span class="sxs-lookup"><span data-stu-id="35f2c-160">HKEY\_CURRENT\_USER\\Software\\Microsoft\\Office\\15.0\\Lync</span></span>

<span data-ttu-id="35f2c-161">REG\_DWORD: SavePassword</span><span class="sxs-lookup"><span data-stu-id="35f2c-161">REG\_DWORD: SavePassword</span></span>

<span data-ttu-id="35f2c-162">Wert: 0x0</span><span class="sxs-lookup"><span data-stu-id="35f2c-162">Value: 0x0</span></span>

</div>

</div>

<div>

## <a name="ad-fs-20-token-replay"></a><span data-ttu-id="35f2c-163">AD FS 2.0-Tokenwiederholung</span><span class="sxs-lookup"><span data-stu-id="35f2c-163">AD FS 2.0 Token Replay</span></span>

<span data-ttu-id="35f2c-p108">AD FS 2.0 stellt eine Funktion bereit, die als Tokenwiederholungserkennung bezeichnet wird und mit welcher mehrere Tokenanforderungen, in denen dasselbe Token verwendet wird, erkannt und verworfen werden können. Ist diese Funktion aktiviert, schützt die Tokenwiederholungserkennung die Integrität von Authentifizierungsanforderungen sowohl im passiven WS-Federation-Profil als auch im SAML WebSSO-Profil, indem sichergestellt wird, dass ein Token nie mehrmals verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="35f2c-p108">AD FS 2.0 provides a feature referred to as token replay detection, by which multiple token requests using the same token can be detected and then discarded. When this feature is enabled, token replay detection protects the integrity of authentication requests in both the WS-Federation passive profile and the SAML WebSSO profile by making sure that the same token is never used more than once.</span></span>

<span data-ttu-id="35f2c-166">Diese Funktion sollte in Umgebungen aktiviert sein, in denen Sicherheit einen besonders hohen Stellenwert hat, beispielsweise bei der Nutzung von Kiosken.</span><span class="sxs-lookup"><span data-stu-id="35f2c-166">This feature should be enabled in situations where security is a very high concern such as when using kiosks.</span></span> <span data-ttu-id="35f2c-167">Weitere Informationen zur Erkennung von Token-Wiedergabe finden Sie unter Bewährte Methoden für die sichere Planung und Bereitstellung von [http://go.microsoft.com/fwlink/p/?LinkId=309215](http://go.microsoft.com/fwlink/p/?linkid=309215)AD FS 2,0 unter.</span><span class="sxs-lookup"><span data-stu-id="35f2c-167">For more information about token replay detection, see Best Practices for Secure Planning and Deployment of AD FS 2.0 at [http://go.microsoft.com/fwlink/p/?LinkId=309215](http://go.microsoft.com/fwlink/p/?linkid=309215).</span></span>

</div>

<div>

## <a name="external-user-access"></a><span data-ttu-id="35f2c-168">Zugriff von externen Benutzern</span><span class="sxs-lookup"><span data-stu-id="35f2c-168">External User Access</span></span>

<span data-ttu-id="35f2c-169">Die Konfiguration eines AD FS-Proxys oder eines Reverse-Proxys zur Unterstützung der zweistufigen lync-Authentifizierung von externen Netzwerken wird in diesen Themen nicht behandelt.</span><span class="sxs-lookup"><span data-stu-id="35f2c-169">Configuring an AD FS Proxy or Reverse Proxy to support Lync two-factor authentication from external networks is not covered in these topics.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

