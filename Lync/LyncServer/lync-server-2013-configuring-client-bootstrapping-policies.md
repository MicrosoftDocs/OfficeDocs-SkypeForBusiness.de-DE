---
title: 'Lync Server 2013: Konfigurieren von clientbootstrapping-Richtlinien'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring client bootstrapping policies
ms:assetid: 45042eca-b845-4207-b12f-b8b7f5d44bdf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425941(v=OCS.15)
ms:contentKeyID: 48184031
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3827bf913c4108c1105376a6f178598a2fb45a06
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/14/2020
ms.locfileid: "41996650"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-client-bootstrapping-policies-in-lync-server-2013"></a><span data-ttu-id="2801f-102">Konfigurieren von clientbootstrapping-Richtlinien in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2801f-102">Configuring client bootstrapping policies in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2801f-103">_**Letztes Änderungsstand des Themas:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="2801f-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="2801f-104">Die Gruppenrichtlinien-Verwaltungskonsole (Group Policy Management Console, GPMC) und der Gruppenrichtlinienobjekt-Editor sind Tools, die Sie zum Verwalten von Gruppenrichtlinien verwenden.</span><span class="sxs-lookup"><span data-stu-id="2801f-104">The Group Policy Management Console (GPMC) and the Group Policy Object Editor are tools that you use to manage Group Policy.</span></span> <span data-ttu-id="2801f-105">Zur administrativen Vorlage für die Office-Gruppenrichtlinie gehören lync 2013. ADMX (ADMX) und. ADML (ADML) administrative Vorlagen, die die registrierungsbasierten Richtlinieneinstellungen enthalten, die Sie für Gruppenrichtlinienobjekte in der Domäne konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="2801f-105">Included with the Office Group Policy Administrative Template are Lync 2013.admx (ADMX) and .adml (ADML) Administrative Templates, which contain the registry-based policy settings that you configure for Group Policy objects in the domain.</span></span> <span data-ttu-id="2801f-106">ADML-Dateien sind sprachspezifische Ergänzungen zu ADMX-Dateien.</span><span class="sxs-lookup"><span data-stu-id="2801f-106">ADML files are language-specific complements to ADMX files.</span></span> <span data-ttu-id="2801f-107">Jede ADMX-und ADML-Datei enthält die Richtlinieneinstellungen für eine einzelne Office-Anwendung.</span><span class="sxs-lookup"><span data-stu-id="2801f-107">Each ADMX and ADML file contains the policy settings for a single Office application.</span></span> <span data-ttu-id="2801f-108">Weitere Informationen finden Sie unter "Office 2013 administrative Template Files (ADMX, ADML)" in der Office 2013-Dokumentation <http://go.microsoft.com/fwlink/p/?linkid=267516>unter.</span><span class="sxs-lookup"><span data-stu-id="2801f-108">For more information, see “Office 2013 Administrative Template files (ADMX, ADML)” in the Office 2013 documentation at <http://go.microsoft.com/fwlink/p/?linkid=267516>.</span></span>

<span data-ttu-id="2801f-109">Für lync 2013 gibt es mehrere clientbootstrapping-Richtlinien, die Sie konfigurieren sollten, bevor sich Benutzer zum ersten Mal beim Server anmelden.</span><span class="sxs-lookup"><span data-stu-id="2801f-109">For Lync 2013, there are several client bootstrapping policies that you should consider configuring before users sign in to the server for the first time.</span></span> <span data-ttu-id="2801f-110">Beispielsweise die Standardserver und der Sicherheitsmodus, die der Client verwenden soll, bis die Anmeldung abgeschlossen ist.</span><span class="sxs-lookup"><span data-stu-id="2801f-110">For example, the default servers and security mode that the client should use until sign-in is complete.</span></span> <span data-ttu-id="2801f-111">Sie können Gruppenrichtlinien verwenden, um diese Einstellungen in den Computer Registrierungen der Benutzer einzurichten, bevor Sie sich anmelden und mit dem Empfang von in-Band-prokonfigurations Einstellungen vom Server beginnen.</span><span class="sxs-lookup"><span data-stu-id="2801f-111">You can use Group Policy to establish these settings in users’ computer registries before they sign in and begin receiving in-band provisioning settings from the server.</span></span> <span data-ttu-id="2801f-112">In der folgenden Tabelle sind die Gruppenrichtlinieneinstellungen aufgeführt, die für lync 2013 verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="2801f-112">The following table lists the Group Policy settings that are available for Lync 2013.</span></span>

### <a name="group-policy-settings-for-lync-2013"></a><span data-ttu-id="2801f-113">Gruppenrichtlinieneinstellungen für Lync 2013</span><span class="sxs-lookup"><span data-stu-id="2801f-113">Group Policy Settings for Lync 2013</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="2801f-114">Gruppenrichtlinieneinstellung</span><span class="sxs-lookup"><span data-stu-id="2801f-114">Group Policy setting</span></span></th>
<th><span data-ttu-id="2801f-115">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="2801f-115">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="2801f-116">Server angeben</span><span class="sxs-lookup"><span data-stu-id="2801f-116">Specify Server</span></span><br />
<span data-ttu-id="2801f-117">(ConfigurationMode)</span><span class="sxs-lookup"><span data-stu-id="2801f-117">(ConfigurationMode)</span></span></p></td>
<td><p><span data-ttu-id="2801f-118">Gibt an, wie lync 2013 den Transport und den Server identifiziert, der während der Anmeldung verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="2801f-118">Specifies how Lync 2013 identifies the transport and server to use during sign-in.</span></span> <span data-ttu-id="2801f-119">In dieser Einstellung geben Sie Folgendes an:</span><span class="sxs-lookup"><span data-stu-id="2801f-119">Within this setting, you specify the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="2801f-120">ServerAddressExternal: gibt den Servernamen oder die IP-Adresse an, die von Clients und verbundkontakten beim Herstellen einer Verbindung von außerhalb der externen Firewall verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="2801f-120">ServerAddressExternal: Specifies the server name or IP address used by clients and federated contacts when connecting from outside the external firewall.</span></span></p></li>
<li><p><span data-ttu-id="2801f-121">ServerAddressInternal: gibt den Servernamen oder die IP-Adresse an, die verwendet wird, wenn Clients innerhalb der Firewall der Organisation eine Verbindung herstellen.</span><span class="sxs-lookup"><span data-stu-id="2801f-121">ServerAddressInternal: Specifies the server name or IP address used when clients connect from inside the organization’s firewall.</span></span></p></li>
<li><p><span data-ttu-id="2801f-122">Transport: gibt entweder TCP (Transmission Control Protocol) oder TLS (Transport Layer Security) an.</span><span class="sxs-lookup"><span data-stu-id="2801f-122">Transport: Specifies either Transmission Control Protocol (TCP) or Transport Layer Security (TLS).</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2801f-123">Unterstützte zusätzliche Server Versionen</span><span class="sxs-lookup"><span data-stu-id="2801f-123">Additional server versions supported</span></span><br />
<span data-ttu-id="2801f-124">(ConfiguredServerCheckValues)</span><span class="sxs-lookup"><span data-stu-id="2801f-124">(ConfiguredServerCheckValues)</span></span></p></td>
<td><p><span data-ttu-id="2801f-125">Gibt eine Liste von Server Versionsnamen an, die durch Semikolons getrennt sind, an denen lync Server 2013 sich anmeldet, zusätzlich zu den standardmäßig unterstützten Server Versionen.</span><span class="sxs-lookup"><span data-stu-id="2801f-125">Specifies a list of server version names separated by semi-colons that Lync Server 2013 will log on to, in addition to the server versions that are supported by default.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2801f-126">Deaktivieren des automatischen Uploads von Anmeldefehler Protokollen (DisableAutomaticSendTracing)</span><span class="sxs-lookup"><span data-stu-id="2801f-126">Disable automatic upload of sign-in failure logs (DisableAutomaticSendTracing)</span></span></p></td>
<td><p><span data-ttu-id="2801f-127">Lädt die Anmeldefehler Protokolle automatisch in lync Server zur Analyse hoch.</span><span class="sxs-lookup"><span data-stu-id="2801f-127">Automatically uploads sign-in failure logs to Lync Server for analysis.</span></span> <span data-ttu-id="2801f-128">Wenn die Anmeldung erfolgreich verläuft, werden keine Protokolle automatisch hochgeladen.</span><span class="sxs-lookup"><span data-stu-id="2801f-128">No logs are automatically uploaded if sign-in is successful.</span></span> <span data-ttu-id="2801f-129">Wenn diese Richtlinie nicht konfiguriert ist, geschieht Folgendes:</span><span class="sxs-lookup"><span data-stu-id="2801f-129">If this policy is not configured, the following happens:</span></span></p>
<dl>
<dt><span></span></dt>
<dd><p><span data-ttu-id="2801f-130">Für lync Online Benutzer: Anmeldefehler Protokolle werden automatisch hochgeladen.</span><span class="sxs-lookup"><span data-stu-id="2801f-130">For Lync Online users: Sign-in failure logs are automatically uploaded.</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="2801f-131">Für lokale lync-Benutzer: dem Benutzer wird vor dem Hochladen ein Bestätigungsdialogfeld angezeigt.</span><span class="sxs-lookup"><span data-stu-id="2801f-131">For Lync on-premises users: A confirmation dialog box is shown to the user before upload.</span></span></p>
</dd>
</dl>
<p><span data-ttu-id="2801f-132">Wenn diese Einstellung deaktiviert ist, werden Anmelde Protokolle automatisch in den lync Server für lokale und lync Online Benutzer von lync hochgeladen.</span><span class="sxs-lookup"><span data-stu-id="2801f-132">When this setting is disabled, sign-in logs are automatically uploaded to the Lync Server for both Lync on-premises and Lync Online users.</span></span> <span data-ttu-id="2801f-133">Wenn diese Einstellung aktiviert ist, werden Anmelde Protokolle nie automatisch hochgeladen.</span><span class="sxs-lookup"><span data-stu-id="2801f-133">When this setting is enabled, sign-in logs are never uploaded automatically.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2801f-134">HTTP-Fallback für SIP-Verbindung deaktivieren</span><span class="sxs-lookup"><span data-stu-id="2801f-134">Disable HTTP fallback for SIP connection</span></span><br />
<span data-ttu-id="2801f-135">(DisableHttpConnect)</span><span class="sxs-lookup"><span data-stu-id="2801f-135">(DisableHttpConnect)</span></span></p></td>
<td><p><span data-ttu-id="2801f-136">Verhindert, dass lync Server versucht, eine Verbindung mit dem Server über HTTP herzustellen, wenn TLS oder TCP nicht verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="2801f-136">Prevents Lync Server from trying to connect to the server by using HTTP, if TLS or TCP are unavailable.</span></span> <span data-ttu-id="2801f-137">Standardmäßig versucht lync zunächst, eine Verbindung mit dem Server mithilfe von TLS oder TCP herzustellen, und wenn keine dieser Transportmethoden erfolgreich ist, versucht lync, eine Verbindung über HTTP herzustellen.</span><span class="sxs-lookup"><span data-stu-id="2801f-137">By default, Lync first attempts to connect to the server by using TLS or TCP and, if neither of these transport methods is successful, Lync tries to connect by using HTTP.</span></span> <span data-ttu-id="2801f-138">Verwenden Sie diese Richtlinie, um die Fallbackoption für den HTTP-Verbindungsversuch zu deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="2801f-138">Use this policy to disable the fallback HTTP connection attempt.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2801f-139">Anmeldeinformationen erforderlich</span><span class="sxs-lookup"><span data-stu-id="2801f-139">Require logon credentials</span></span><br />
<span data-ttu-id="2801f-140">DisableNTCredentials</span><span class="sxs-lookup"><span data-stu-id="2801f-140">(DisableNTCredentials)</span></span></p></td>
<td><p><span data-ttu-id="2801f-141">Erfordert, dass der Benutzeranmeldeinformationen für lync bereitstellt, anstatt die Windows-Anmeldeinformationen bei der Anmeldung bei einem SIP-Server automatisch zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="2801f-141">Requires the user to provide logon credentials for Lync rather than automatically using Windows credentials during sign-in to a SIP server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2801f-142">Deaktivieren der Server Versionsüberprüfung</span><span class="sxs-lookup"><span data-stu-id="2801f-142">Disable server version check</span></span><br />
<span data-ttu-id="2801f-143">(DisableServerCheck)</span><span class="sxs-lookup"><span data-stu-id="2801f-143">(DisableServerCheck)</span></span></p></td>
<td><p><span data-ttu-id="2801f-144">Wenn Sie diese Richtlinie auf 1 festlegen, wird verhindert, dass lync den Servernamen und die Version überprüft, bevor Sie sich anmelden.</span><span class="sxs-lookup"><span data-stu-id="2801f-144">If you set this policy to 1, prevents Lync from checking the server name and version before signing in.</span></span> <span data-ttu-id="2801f-145">Standardmäßig führt lync diese Prüfungen aus, bevor er sich anmeldet.</span><span class="sxs-lookup"><span data-stu-id="2801f-145">By default, Lync makes these checks before signing in.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2801f-146">Aktivieren der Verwendung von Bits zum Herunterladen von Adressbuchdienst Dateien</span><span class="sxs-lookup"><span data-stu-id="2801f-146">Enable using BITS to download Address Book Service files</span></span><br />
<span data-ttu-id="2801f-147">(EnableBitsForGalDownload)</span><span class="sxs-lookup"><span data-stu-id="2801f-147">(EnableBitsForGalDownload)</span></span></p></td>
<td><p><span data-ttu-id="2801f-148">Ermöglicht lync die Verwendung des Background Intelligent Transfer Service (Bits) zum Herunterladen der Adressbuchdienste-Dateien.</span><span class="sxs-lookup"><span data-stu-id="2801f-148">Enables Lync to use Background Intelligent Transfer Service (BITS) to download the Address Book Services files.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2801f-149">Konfigurieren des SIP-Sicherheitsmodus</span><span class="sxs-lookup"><span data-stu-id="2801f-149">Configure SIP security mode</span></span><br />
<span data-ttu-id="2801f-150">(EnableSIPHighSecurityMode)</span><span class="sxs-lookup"><span data-stu-id="2801f-150">(EnableSIPHighSecurityMode)</span></span></p></td>
<td><p><span data-ttu-id="2801f-151">Ermöglicht lync das sichere Senden und empfangen von Sofortnachrichten.</span><span class="sxs-lookup"><span data-stu-id="2801f-151">Enables Lync to send and receive instant messages more securely.</span></span> <span data-ttu-id="2801f-152">Diese Richtlinie hat keine Auswirkung auf Windows .NET- oder Microsoft Exchange Server-Dienste.</span><span class="sxs-lookup"><span data-stu-id="2801f-152">This policy has no effect on Windows .NET or Microsoft Exchange Server services.</span></span></p>
<p><span data-ttu-id="2801f-153">Wenn Sie diese Richtlinieneinstellung nicht konfigurieren, kann lync einen beliebigen Transport verwenden.</span><span class="sxs-lookup"><span data-stu-id="2801f-153">If you do not configure this policy setting, Lync can use any transport.</span></span> <span data-ttu-id="2801f-154">Wenn jedoch TLS nicht verwendet wird und der Server Benutzer authentifiziert, muss lync entweder NTLM oder Kerberos-Authentifizierung verwenden.</span><span class="sxs-lookup"><span data-stu-id="2801f-154">But if it does not use TLS and if the server authenticates users, Lync must use either NTLM or Kerberos authentication.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2801f-155">Anfängliche Verzögerung für das globale Adressbuch herunterladen</span><span class="sxs-lookup"><span data-stu-id="2801f-155">Global Address Book Download Initial Delay</span></span><br />
<span data-ttu-id="2801f-156">GalDownloadInitialDelay</span><span class="sxs-lookup"><span data-stu-id="2801f-156">(GalDownloadInitialDelay)</span></span></p></td>
<td><p><span data-ttu-id="2801f-157">Gibt den Zeitraum an, vor dem ein Download der globalen Adressliste (GAL) erfolgt.</span><span class="sxs-lookup"><span data-stu-id="2801f-157">Specifies the time period before a download of the global address list (GAL) occurs.</span></span> <span data-ttu-id="2801f-158">Der Standardwert ist 60 Minuten, was bedeutet, dass der Server den Download der GAL-Datei für einen zufälligen Zeitraum zwischen 0 und 60 Minuten verzögert.</span><span class="sxs-lookup"><span data-stu-id="2801f-158">The default value is 60 minutes, which means the server delays the download of GAL file for a random period of between 0 and 60 minutes.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2801f-159">Verhindern der Ausführung von Microsoft lync durch Benutzer</span><span class="sxs-lookup"><span data-stu-id="2801f-159">Prevent users from running Microsoft Lync</span></span><br />
<span data-ttu-id="2801f-160">(PreventRun)</span><span class="sxs-lookup"><span data-stu-id="2801f-160">(PreventRun)</span></span></p></td>
<td><p><span data-ttu-id="2801f-161">Verhindert, dass Benutzer lync durchführen.</span><span class="sxs-lookup"><span data-stu-id="2801f-161">Prevents users from running Lync.</span></span> <span data-ttu-id="2801f-162">Diese Richtlinieneinstellung kann sowohl in der Computerkonfiguration als auch in der Benutzerkonfiguration vorgenommen werden, die Einstellung in der Computerkonfiguration hat jedoch Vorrang.</span><span class="sxs-lookup"><span data-stu-id="2801f-162">You can configure this policy setting under both Computer Configuration and User Configuration, but the policy setting under Computer Configuration takes precedence.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2801f-163">Zulassen der Speicherung von Benutzerkennwörtern</span><span class="sxs-lookup"><span data-stu-id="2801f-163">Allow storage of user passwords</span></span><br />
<span data-ttu-id="2801f-164">SavePassword</span><span class="sxs-lookup"><span data-stu-id="2801f-164">(SavePassword)</span></span></p></td>
<td><p><span data-ttu-id="2801f-165">Ermöglicht lync das Speichern von Kennwörtern.</span><span class="sxs-lookup"><span data-stu-id="2801f-165">Enables Lync to store passwords.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2801f-166">Konfigurieren des SIP-Komprimierungsmodus</span><span class="sxs-lookup"><span data-stu-id="2801f-166">Configure SIP compression mode</span></span><br />
<span data-ttu-id="2801f-167">(SipCompression)</span><span class="sxs-lookup"><span data-stu-id="2801f-167">(SipCompression)</span></span></p></td>
<td><p><span data-ttu-id="2801f-p112">Legt fest, wann die SIP-Komprimierung aktiviert wird. Die SIP-Komprimierung wird standardmäßig auf Grundlage der Adaptergeschwindigkeit aktiviert. Beachten Sie, dass die Festlegung dieser Richtlinie die Anmeldezeit verlängern kann.</span><span class="sxs-lookup"><span data-stu-id="2801f-p112">Specifies when to turn on SIP compression. By default, SIP compression is enabled based on the adapter speed. Note that setting this policy might cause an increase in sign-in time.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2801f-171">Liste vertrauenswürdiger Domänen</span><span class="sxs-lookup"><span data-stu-id="2801f-171">Trusted Domain List</span></span><br />
<span data-ttu-id="2801f-172">(TrustModelData)</span><span class="sxs-lookup"><span data-stu-id="2801f-172">(TrustModelData)</span></span></p></td>
<td><p><span data-ttu-id="2801f-173">Listet die vertrauenswürdigen Domänen auf, die nicht mit dem Präfix der SIP-Domäne des Kunden übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="2801f-173">Lists the trusted domains that do not match the prefix of the customer SIP domain.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="2801f-p113">Auf dem Server konfigurierte Richtlinien haben Vorrang vor Gruppenrichtlinieneinstellungen und Clientoptionen, die vom Benutzer konfiguriert wurden. In der folgenden Tabelle wird zusammengefasst, welche Einstellungen Vorrang haben, falls ein Konflikt auftritt.</span><span class="sxs-lookup"><span data-stu-id="2801f-p113">Policies configured on the server take precedence over Group Policy settings and client options configured by the user. The following table summarizes the order in which settings take precedence when a conflict occurs.</span></span>

### <a name="group-policy-precedence"></a><span data-ttu-id="2801f-176">Rangfolge von Gruppenrichtlinien</span><span class="sxs-lookup"><span data-stu-id="2801f-176">Group Policy Precedence</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="2801f-177">Vorrang</span><span class="sxs-lookup"><span data-stu-id="2801f-177">Precedence</span></span></th>
<th><span data-ttu-id="2801f-178">Ort oder Einstellungsmethode</span><span class="sxs-lookup"><span data-stu-id="2801f-178">Location or Method of Setting</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="2801f-179">1 </span><span class="sxs-lookup"><span data-stu-id="2801f-179">1</span></span></p></td>
<td><p><span data-ttu-id="2801f-180">Lync Server 2013-in-Band-prozielung</span><span class="sxs-lookup"><span data-stu-id="2801f-180">Lync Server 2013 in-band provisioning</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2801f-181">2 </span><span class="sxs-lookup"><span data-stu-id="2801f-181">2</span></span></p></td>
<td><p><span data-ttu-id="2801f-182">HKEY_LOCAL_MACHINE \software\policies\microsoft\office\15.0\lync</span><span class="sxs-lookup"><span data-stu-id="2801f-182">HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Office\15.0\Lync</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2801f-183">3 </span><span class="sxs-lookup"><span data-stu-id="2801f-183">3</span></span></p></td>
<td><p><span data-ttu-id="2801f-184">HKEY_CURRENT_USER \software\policies\microsoft\office\15.0\lync</span><span class="sxs-lookup"><span data-stu-id="2801f-184">HKEY_CURRENT_USER\SOFTWARE\Policies\Microsoft\Office\15.0\Lync</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2801f-185">4 </span><span class="sxs-lookup"><span data-stu-id="2801f-185">4</span></span></p></td>
<td><p><span data-ttu-id="2801f-186">Das Dialogfeld lync-Optionen in lync 2013</span><span class="sxs-lookup"><span data-stu-id="2801f-186">The Lync - Options dialog box in Lync 2013</span></span></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="to-define-group-policy-settings-by-using-the-lync-2013-administrative-template-files"></a><span data-ttu-id="2801f-187">So definieren Sie Gruppenrichtlinieneinstellungen mithilfe der lync 2013 administrativen Vorlagendateien</span><span class="sxs-lookup"><span data-stu-id="2801f-187">To define Group Policy settings by using the Lync 2013 administrative template files</span></span>

1.  <span data-ttu-id="2801f-188">Erstellen Sie einen Ordner auf Stammebene, der alle sprachneutralen ADMX-Dateien enthält.</span><span class="sxs-lookup"><span data-stu-id="2801f-188">Create a root-level folder to contain all language-neutral ADMX files.</span></span> <span data-ttu-id="2801f-189">Erstellen Sie den Stammordner für den zentralen Speicher beispielsweise auf dem Domänencontroller an folgendem Speicherort:</span><span class="sxs-lookup"><span data-stu-id="2801f-189">For example, create the root folder for the central store on your domain controller at this location:</span></span>
    
    `%systemroot%\sysvol\domain\policies\PolicyDefinitions`
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="2801f-190">Bei diesem Verfahren wird davon ausgegangen, dass Sie mehrere Computer in Ihrer Domäne verwalten möchten.</span><span class="sxs-lookup"><span data-stu-id="2801f-190">This procedure assumes that you want to manage multiple computers in your domain.</span></span> <span data-ttu-id="2801f-191">In diesem Fall speichern Sie die Vorlagen in einem zentralen Speicher im Ordner "SYSVOL" auf dem primären Domänencontroller.</span><span class="sxs-lookup"><span data-stu-id="2801f-191">In this case, you store the templates in a central store in the Sysvol folder on the primary domain controller.</span></span> <span data-ttu-id="2801f-192">Dadurch wird ein replizierter zentraler Speicherort für administrative Domänen Vorlagen bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="2801f-192">This provides a replicated central storage location for domain Administrative Templates.</span></span>

    
    </div>

2.  <span data-ttu-id="2801f-193">Erstellen Sie einen Unterordner für jede Sprache, die Sie verwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="2801f-193">Create a subfolder for each language that you’ll use.</span></span> <span data-ttu-id="2801f-194">Diese Unterordner enthalten die sprachspezifischen ADML-Ressourcendateien.</span><span class="sxs-lookup"><span data-stu-id="2801f-194">These subfolders will contain the language-specific ADML resource files.</span></span> <span data-ttu-id="2801f-195">Erstellen Sie an dieser Stelle beispielsweise einen Unterordner für Englisch (en-US) für Deutschland:</span><span class="sxs-lookup"><span data-stu-id="2801f-195">For example, create a subfolder for United States English (EN-US) at this location:</span></span>
    
    `%systemroot%\sysvol\domain\policies\PolicyDefinitions\EN-US`

</div>

</div>

<span> </span>

</div>

</div>

</div>

