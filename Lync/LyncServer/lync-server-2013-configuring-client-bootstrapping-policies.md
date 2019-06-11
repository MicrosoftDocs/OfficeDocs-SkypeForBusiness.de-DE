---
title: 'Lync Server 2013: Konfigurieren von Client-Trap Ping-Richtlinien'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring client bootstrapping policies
ms:assetid: 45042eca-b845-4207-b12f-b8b7f5d44bdf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425941(v=OCS.15)
ms:contentKeyID: 48184031
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 06119d5488b47adfe01a934aca9a55581feaf33e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34839288"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-client-bootstrapping-policies-in-lync-server-2013"></a><span data-ttu-id="46ba7-102">Konfigurieren von Client-Trap Ping-Richtlinien in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="46ba7-102">Configuring client bootstrapping policies in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="46ba7-103">_**Letztes Änderungsdatum des Themas:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="46ba7-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="46ba7-104">Die Gruppenrichtlinien-Verwaltungskonsole (Group Policy Management Console, GPMC) und der Gruppenrichtlinienobjekt-Editor sind Tools zur Verwaltung von Gruppenrichtlinien.</span><span class="sxs-lookup"><span data-stu-id="46ba7-104">The Group Policy Management Console (GPMC) and the Group Policy Object Editor are tools that you use to manage Group Policy.</span></span> <span data-ttu-id="46ba7-105">In der administrativen Vorlage für Office-Gruppenrichtlinien sind lync 2013. ADMX (ADMX)-und ADML (ADML)-administrative Vorlagen enthalten, die die registrierungsbasierten Richtlinieneinstellungen enthalten, die Sie für Gruppenrichtlinienobjekte in der Domäne konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="46ba7-105">Included with the Office Group Policy Administrative Template are Lync 2013.admx (ADMX) and .adml (ADML) Administrative Templates, which contain the registry-based policy settings that you configure for Group Policy objects in the domain.</span></span> <span data-ttu-id="46ba7-106">ADML-Dateien sind sprachspezifische Komplemente für ADMX-Dateien.</span><span class="sxs-lookup"><span data-stu-id="46ba7-106">ADML files are language-specific complements to ADMX files.</span></span> <span data-ttu-id="46ba7-107">Jede ADMX- und ADML-Datei enthält die Richtlinieneinstellungen für eine einzelne Office-Anwendung.</span><span class="sxs-lookup"><span data-stu-id="46ba7-107">Each ADMX and ADML file contains the policy settings for a single Office application.</span></span> <span data-ttu-id="46ba7-108">Weitere Informationen finden Sie unter "Office 2013 administrative Template Files (ADMX, ADML)" in der Office 2013-Dokumentation <http://go.microsoft.com/fwlink/p/?linkid=267516>unter.</span><span class="sxs-lookup"><span data-stu-id="46ba7-108">For more information, see “Office 2013 Administrative Template files (ADMX, ADML)” in the Office 2013 documentation at <http://go.microsoft.com/fwlink/p/?linkid=267516>.</span></span>

<span data-ttu-id="46ba7-109">Für lync 2013 gibt es mehrere Richtlinien für Client-Bootstrapping, die Sie konfigurieren sollten, bevor sich Benutzer zum ersten Mal beim Server anmelden.</span><span class="sxs-lookup"><span data-stu-id="46ba7-109">For Lync 2013, there are several client bootstrapping policies that you should consider configuring before users sign in to the server for the first time.</span></span> <span data-ttu-id="46ba7-110">Dazu gehören die Standardserver und der Sicherheitsmodus, die der Client bis zum Abschluss der Anmeldung verwenden soll.</span><span class="sxs-lookup"><span data-stu-id="46ba7-110">For example, the default servers and security mode that the client should use until sign-in is complete.</span></span> <span data-ttu-id="46ba7-111">Sie können die Gruppenrichtlinie verwenden, um diese Einstellungen in den Registrierungen der Computer von Benutzern vorzunehmen, bevor diese sich anmelden und erstmals In-Band-Bereitstellungseinstellungen vom Server empfangen.</span><span class="sxs-lookup"><span data-stu-id="46ba7-111">You can use Group Policy to establish these settings in users’ computer registries before they sign in and begin receiving in-band provisioning settings from the server.</span></span> <span data-ttu-id="46ba7-112">In der folgenden Tabelle sind die Gruppenrichtlinieneinstellungen aufgeführt, die für lync 2013 verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="46ba7-112">The following table lists the Group Policy settings that are available for Lync 2013.</span></span>

### <a name="group-policy-settings-for-lync-2013"></a><span data-ttu-id="46ba7-113">Gruppenrichtlinieneinstellungen für lync 2013</span><span class="sxs-lookup"><span data-stu-id="46ba7-113">Group Policy Settings for Lync 2013</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="46ba7-114">Gruppenrichtlinieneinstellung</span><span class="sxs-lookup"><span data-stu-id="46ba7-114">Group Policy setting</span></span></th>
<th><span data-ttu-id="46ba7-115">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="46ba7-115">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="46ba7-116">Server angeben</span><span class="sxs-lookup"><span data-stu-id="46ba7-116">Specify Server</span></span><br />
<span data-ttu-id="46ba7-117">(ConfigurationMode)</span><span class="sxs-lookup"><span data-stu-id="46ba7-117">(ConfigurationMode)</span></span></p></td>
<td><p><span data-ttu-id="46ba7-118">Gibt an, wie lync 2013 den Transport und den Server identifiziert, die bei der Anmeldung zu verwenden sind.</span><span class="sxs-lookup"><span data-stu-id="46ba7-118">Specifies how Lync 2013 identifies the transport and server to use during sign-in.</span></span> <span data-ttu-id="46ba7-119">In dieser Einstellung geben Sie Folgendes an:</span><span class="sxs-lookup"><span data-stu-id="46ba7-119">Within this setting, you specify the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="46ba7-120">ServerAddressExternal: Gibt den Servernamen oder die IP-Adresse an, der bzw. die von Clients und Verbundkontakten verwendet wird, um von außerhalb der Firewall eine Verbindung herzustellen.</span><span class="sxs-lookup"><span data-stu-id="46ba7-120">ServerAddressExternal: Specifies the server name or IP address used by clients and federated contacts when connecting from outside the external firewall.</span></span></p></li>
<li><p><span data-ttu-id="46ba7-121">ServerAddressInternal: Gibt den Servernamen oder die IP-Adresse an, der bzw. die verwendet wird, wenn Clients eine Verbindung von innerhalb der Unternehmensfirewall herstellen.</span><span class="sxs-lookup"><span data-stu-id="46ba7-121">ServerAddressInternal: Specifies the server name or IP address used when clients connect from inside the organization’s firewall.</span></span></p></li>
<li><p><span data-ttu-id="46ba7-122">Transport: Gibt entweder TCP (Transmission Control Protocol) oder TLS (Transport Layer Security) an.</span><span class="sxs-lookup"><span data-stu-id="46ba7-122">Transport: Specifies either Transmission Control Protocol (TCP) or Transport Layer Security (TLS).</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="46ba7-123">Zusätzliche Server Versionen unterstützt</span><span class="sxs-lookup"><span data-stu-id="46ba7-123">Additional server versions supported</span></span><br />
<span data-ttu-id="46ba7-124">(ConfiguredServerCheckValues)</span><span class="sxs-lookup"><span data-stu-id="46ba7-124">(ConfiguredServerCheckValues)</span></span></p></td>
<td><p><span data-ttu-id="46ba7-125">Gibt eine Liste der Server Versionsnamen an, die durch Semikolons getrennt sind, bei denen sich lync Server 2013 zusätzlich zu den standardmäßig unterstützten Server Versionen anmeldet.</span><span class="sxs-lookup"><span data-stu-id="46ba7-125">Specifies a list of server version names separated by semi-colons that Lync Server 2013 will log on to, in addition to the server versions that are supported by default.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="46ba7-126">Automatisches Hochladen von Anmeldefehlerprotokollen deaktivieren (DisableAutomaticSendTracing)</span><span class="sxs-lookup"><span data-stu-id="46ba7-126">Disable automatic upload of sign-in failure logs (DisableAutomaticSendTracing)</span></span></p></td>
<td><p><span data-ttu-id="46ba7-127">Automatisches Hochladen von Anmeldefehler Protokollen zur Analyse in lync Server.</span><span class="sxs-lookup"><span data-stu-id="46ba7-127">Automatically uploads sign-in failure logs to Lync Server for analysis.</span></span> <span data-ttu-id="46ba7-128">Bei erfolgreichen Anmeldungen werden keine Protokolle automatisch hochgeladen.</span><span class="sxs-lookup"><span data-stu-id="46ba7-128">No logs are automatically uploaded if sign-in is successful.</span></span> <span data-ttu-id="46ba7-129">Wenn diese Richtlinie nicht konfiguriert ist, geschieht Folgendes:</span><span class="sxs-lookup"><span data-stu-id="46ba7-129">If this policy is not configured, the following happens:</span></span></p>
<dl>
<dt><span></span></dt>
<dd><p><span data-ttu-id="46ba7-130">Für lync Online-Benutzer: Anmeldefehler Protokolle werden automatisch hochgeladen.</span><span class="sxs-lookup"><span data-stu-id="46ba7-130">For Lync Online users: Sign-in failure logs are automatically uploaded.</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="46ba7-131">Für lokale lync-Benutzer: dem Benutzer wird vor dem Hochladen ein Bestätigungsdialogfeld angezeigt.</span><span class="sxs-lookup"><span data-stu-id="46ba7-131">For Lync on-premises users: A confirmation dialog box is shown to the user before upload.</span></span></p>
</dd>
</dl>
<p><span data-ttu-id="46ba7-132">Wenn diese Einstellung deaktiviert ist, werden Anmelde Protokolle automatisch für lync-lokale und lync Online-Benutzer auf den lync-Server hochgeladen.</span><span class="sxs-lookup"><span data-stu-id="46ba7-132">When this setting is disabled, sign-in logs are automatically uploaded to the Lync Server for both Lync on-premises and Lync Online users.</span></span> <span data-ttu-id="46ba7-133">Wenn diese Einstellung aktiviert ist, werden Anmeldeprotokolle niemals automatisch hochgeladen.</span><span class="sxs-lookup"><span data-stu-id="46ba7-133">When this setting is enabled, sign-in logs are never uploaded automatically.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="46ba7-134">Deaktivieren des http-Fallbacks für die SIP-Verbindung</span><span class="sxs-lookup"><span data-stu-id="46ba7-134">Disable HTTP fallback for SIP connection</span></span><br />
<span data-ttu-id="46ba7-135">(DisableHttpConnect)</span><span class="sxs-lookup"><span data-stu-id="46ba7-135">(DisableHttpConnect)</span></span></p></td>
<td><p><span data-ttu-id="46ba7-136">Verhindert, dass lync Server versucht, eine Verbindung mit dem Server über HTTP herzustellen, wenn TLS oder TCP nicht verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="46ba7-136">Prevents Lync Server from trying to connect to the server by using HTTP, if TLS or TCP are unavailable.</span></span> <span data-ttu-id="46ba7-137">Standardmäßig versucht lync zunächst, mithilfe von TLS oder TCP eine Verbindung mit dem Server herzustellen, und wenn keine dieser Transportmethoden erfolgreich ist, versucht lync, eine Verbindung über HTTP herzustellen.</span><span class="sxs-lookup"><span data-stu-id="46ba7-137">By default, Lync first attempts to connect to the server by using TLS or TCP and, if neither of these transport methods is successful, Lync tries to connect by using HTTP.</span></span> <span data-ttu-id="46ba7-138">Verwenden Sie diese Richtlinie, um den Fall Back http-Verbindungsversuch zu deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="46ba7-138">Use this policy to disable the fallback HTTP connection attempt.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="46ba7-139">Anmeldeinformationen erforderlich</span><span class="sxs-lookup"><span data-stu-id="46ba7-139">Require logon credentials</span></span><br />
<span data-ttu-id="46ba7-140">(DisableNTCredentials)</span><span class="sxs-lookup"><span data-stu-id="46ba7-140">(DisableNTCredentials)</span></span></p></td>
<td><p><span data-ttu-id="46ba7-141">Erfordert, dass der Benutzeranmeldeinformationen für lync bereitstellt, anstatt die Windows-Anmeldeinformationen bei der Anmeldung bei einem SIP-Server automatisch zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="46ba7-141">Requires the user to provide logon credentials for Lync rather than automatically using Windows credentials during sign-in to a SIP server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="46ba7-142">Deaktivieren der Server Versionsüberprüfung</span><span class="sxs-lookup"><span data-stu-id="46ba7-142">Disable server version check</span></span><br />
<span data-ttu-id="46ba7-143">(DisableServerCheck)</span><span class="sxs-lookup"><span data-stu-id="46ba7-143">(DisableServerCheck)</span></span></p></td>
<td><p><span data-ttu-id="46ba7-144">Wenn Sie diese Richtlinie auf 1 festlegen, wird verhindert, dass lync den Servernamen und die Version überprüft, bevor Sie sich anmelden.</span><span class="sxs-lookup"><span data-stu-id="46ba7-144">If you set this policy to 1, prevents Lync from checking the server name and version before signing in.</span></span> <span data-ttu-id="46ba7-145">Standardmäßig führt lync diese Prüfungen aus, bevor Sie sich anmelden.</span><span class="sxs-lookup"><span data-stu-id="46ba7-145">By default, Lync makes these checks before signing in.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="46ba7-146">Aktivieren der Verwendung von Bits zum Herunterladen von Adressbuchdienst Dateien</span><span class="sxs-lookup"><span data-stu-id="46ba7-146">Enable using BITS to download Address Book Service files</span></span><br />
<span data-ttu-id="46ba7-147">(EnableBitsForGalDownload)</span><span class="sxs-lookup"><span data-stu-id="46ba7-147">(EnableBitsForGalDownload)</span></span></p></td>
<td><p><span data-ttu-id="46ba7-148">Ermöglicht lync die Verwendung von Bits (Background Intelligent Transfer Service) zum Herunterladen der Adressbuchdienste-Dateien.</span><span class="sxs-lookup"><span data-stu-id="46ba7-148">Enables Lync to use Background Intelligent Transfer Service (BITS) to download the Address Book Services files.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="46ba7-149">Konfigurieren des SIP-Sicherheitsmodus</span><span class="sxs-lookup"><span data-stu-id="46ba7-149">Configure SIP security mode</span></span><br />
<span data-ttu-id="46ba7-150">(EnableSIPHighSecurityMode)</span><span class="sxs-lookup"><span data-stu-id="46ba7-150">(EnableSIPHighSecurityMode)</span></span></p></td>
<td><p><span data-ttu-id="46ba7-151">Ermöglicht lync das sichere Senden und empfangen von Sofortnachrichten.</span><span class="sxs-lookup"><span data-stu-id="46ba7-151">Enables Lync to send and receive instant messages more securely.</span></span> <span data-ttu-id="46ba7-152">Diese Richtlinie hat keine Auswirkung auf Windows .NET- oder Microsoft Exchange Server-Dienste.</span><span class="sxs-lookup"><span data-stu-id="46ba7-152">This policy has no effect on Windows .NET or Microsoft Exchange Server services.</span></span></p>
<p><span data-ttu-id="46ba7-153">Wenn Sie diese Richtlinieneinstellung nicht konfigurieren, kann lync einen beliebigen Transport verwenden.</span><span class="sxs-lookup"><span data-stu-id="46ba7-153">If you do not configure this policy setting, Lync can use any transport.</span></span> <span data-ttu-id="46ba7-154">Wenn Sie aber nicht TLS verwenden und der Server Benutzer authentifiziert, muss lync entweder NTLM-oder Kerberos-Authentifizierung verwenden.</span><span class="sxs-lookup"><span data-stu-id="46ba7-154">But if it does not use TLS and if the server authenticates users, Lync must use either NTLM or Kerberos authentication.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="46ba7-155">Download des globalen Adressbuchs Anfangsverzögerung</span><span class="sxs-lookup"><span data-stu-id="46ba7-155">Global Address Book Download Initial Delay</span></span><br />
<span data-ttu-id="46ba7-156">GalDownloadInitialDelay</span><span class="sxs-lookup"><span data-stu-id="46ba7-156">(GalDownloadInitialDelay)</span></span></p></td>
<td><p><span data-ttu-id="46ba7-p110">Legt den Zeitraum bis zum Download der globalen Adressliste (GAL) fest. Der Standardwert beträgt 60 Minuten, d. h., der Server verzögert den Download der globalen Adressliste um einen zufälligen Zeitraum zwischen 0 und 60 Minuten.</span><span class="sxs-lookup"><span data-stu-id="46ba7-p110">Specifies the time period before a download of the global address list (GAL) occurs. The default value is 60 minutes, which means the server delays the download of GAL file for a random period of between 0 and 60 minutes.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="46ba7-159">Verhindern, dass Benutzer Microsoft lync ausführen</span><span class="sxs-lookup"><span data-stu-id="46ba7-159">Prevent users from running Microsoft Lync</span></span><br />
<span data-ttu-id="46ba7-160">(PreventRun)</span><span class="sxs-lookup"><span data-stu-id="46ba7-160">(PreventRun)</span></span></p></td>
<td><p><span data-ttu-id="46ba7-161">Verhindert, dass Benutzer lync ausführen.</span><span class="sxs-lookup"><span data-stu-id="46ba7-161">Prevents users from running Lync.</span></span> <span data-ttu-id="46ba7-162">Sie können diese Richtlinieneinstellung unter Computerkonfiguration und Benutzerkonfiguration konfigurieren, aber die Richtlinieneinstellung unter Computerkonfiguration hat Vorrang.</span><span class="sxs-lookup"><span data-stu-id="46ba7-162">You can configure this policy setting under both Computer Configuration and User Configuration, but the policy setting under Computer Configuration takes precedence.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="46ba7-163">Speichern von Benutzerkennwörtern zulassen</span><span class="sxs-lookup"><span data-stu-id="46ba7-163">Allow storage of user passwords</span></span><br />
<span data-ttu-id="46ba7-164">(SavePassword)</span><span class="sxs-lookup"><span data-stu-id="46ba7-164">(SavePassword)</span></span></p></td>
<td><p><span data-ttu-id="46ba7-165">Ermöglicht lync das Speichern von Kennwörtern.</span><span class="sxs-lookup"><span data-stu-id="46ba7-165">Enables Lync to store passwords.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="46ba7-166">Konfigurieren des SIP-Komprimierungsmodus</span><span class="sxs-lookup"><span data-stu-id="46ba7-166">Configure SIP compression mode</span></span><br />
<span data-ttu-id="46ba7-167">(SipCompression)</span><span class="sxs-lookup"><span data-stu-id="46ba7-167">(SipCompression)</span></span></p></td>
<td><p><span data-ttu-id="46ba7-p112">Gibt an, wann die SIP-Komprimierung aktiviert wird. Die SIP-Komprimierung wird standardmäßig auf Grundlage der Adaptergeschwindigkeit aktiviert. Beachten Sie, dass die Festlegung dieser Richtlinie die Anmeldezeit verlängern kann.</span><span class="sxs-lookup"><span data-stu-id="46ba7-p112">Specifies when to turn on SIP compression. By default, SIP compression is enabled based on the adapter speed. Note that setting this policy might cause an increase in sign-in time.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="46ba7-171">Liste der vertrauenswürdigen Domänen</span><span class="sxs-lookup"><span data-stu-id="46ba7-171">Trusted Domain List</span></span><br />
<span data-ttu-id="46ba7-172">TrustModelData</span><span class="sxs-lookup"><span data-stu-id="46ba7-172">(TrustModelData)</span></span></p></td>
<td><p><span data-ttu-id="46ba7-173">Listet die vertrauenswürdigen Domänen auf, die nicht mit dem Präfix der SIP-Domäne des Kunden übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="46ba7-173">Lists the trusted domains that do not match the prefix of the customer SIP domain.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="46ba7-p113">Auf dem Server konfigurierte Richtlinien haben Vorrang vor Gruppenrichtlinieneinstellungen und Clientoptionen, die vom Benutzer konfiguriert wurden. In der folgenden Tabelle wird zusammengefasst, welche Einstellungen Vorrang haben, falls ein Konflikt auftritt.</span><span class="sxs-lookup"><span data-stu-id="46ba7-p113">Policies configured on the server take precedence over Group Policy settings and client options configured by the user. The following table summarizes the order in which settings take precedence when a conflict occurs.</span></span>

### <a name="group-policy-precedence"></a><span data-ttu-id="46ba7-176">Rangfolge von Gruppenrichtlinien</span><span class="sxs-lookup"><span data-stu-id="46ba7-176">Group Policy Precedence</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="46ba7-177">Rangfolge</span><span class="sxs-lookup"><span data-stu-id="46ba7-177">Precedence</span></span></th>
<th><span data-ttu-id="46ba7-178">Ort oder Einstellungsmethode</span><span class="sxs-lookup"><span data-stu-id="46ba7-178">Location or Method of Setting</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="46ba7-179">1</span><span class="sxs-lookup"><span data-stu-id="46ba7-179">1</span></span></p></td>
<td><p><span data-ttu-id="46ba7-180">Lync Server 2013-in-Band-Bereitstellung</span><span class="sxs-lookup"><span data-stu-id="46ba7-180">Lync Server 2013 in-band provisioning</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="46ba7-181">2</span><span class="sxs-lookup"><span data-stu-id="46ba7-181">2</span></span></p></td>
<td><p><span data-ttu-id="46ba7-182">HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Office\15.0\Lync</span><span class="sxs-lookup"><span data-stu-id="46ba7-182">HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Office\15.0\Lync</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="46ba7-183">3</span><span class="sxs-lookup"><span data-stu-id="46ba7-183">3</span></span></p></td>
<td><p><span data-ttu-id="46ba7-184">HKEY_CURRENT_USER\SOFTWARE\Policies\Microsoft\Office\15.0\Lync</span><span class="sxs-lookup"><span data-stu-id="46ba7-184">HKEY_CURRENT_USER\SOFTWARE\Policies\Microsoft\Office\15.0\Lync</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="46ba7-185">4</span><span class="sxs-lookup"><span data-stu-id="46ba7-185">4</span></span></p></td>
<td><p><span data-ttu-id="46ba7-186">Das Dialogfeld "lync-Optionen" in lync 2013</span><span class="sxs-lookup"><span data-stu-id="46ba7-186">The Lync - Options dialog box in Lync 2013</span></span></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="to-define-group-policy-settings-by-using-the-lync-2013-administrative-template-files"></a><span data-ttu-id="46ba7-187">So definieren Sie Gruppenrichtlinieneinstellungen mithilfe der administrativen Vorlagendateien von lync 2013</span><span class="sxs-lookup"><span data-stu-id="46ba7-187">To define Group Policy settings by using the Lync 2013 administrative template files</span></span>

1.  <span data-ttu-id="46ba7-p114">Erstellen Sie einen Ordner auf Stammebene, der alle sprachneutralen ADMX-Dateien enthalten soll. Erstellen Sie beispielsweise den Stammordner für den zentralen Speicher auf Ihrem Domänencontroller an folgendem Speicherort:</span><span class="sxs-lookup"><span data-stu-id="46ba7-p114">Create a root-level folder to contain all language-neutral ADMX files. For example, create the root folder for the central store on your domain controller at this location:</span></span>
    
    `%systemroot%\sysvol\domain\policies\PolicyDefinitions`
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="46ba7-p115">Bei diesem Verfahren wird angenommen, dass Sie in Ihrer Domäne mehrere Computer verwalten möchten. Speichern Sie in diesem Fall die Vorlagen in einem zentralen Speicher im Ordner "Sysvol" auf dem primären Domänencontroller. Dies schafft einen replizierten zentralen Speicherort für administrative Domänenvorlagen.</span><span class="sxs-lookup"><span data-stu-id="46ba7-p115">This procedure assumes that you want to manage multiple computers in your domain. In this case, you store the templates in a central store in the Sysvol folder on the primary domain controller. This provides a replicated central storage location for domain Administrative Templates.</span></span>

    
    </div>

2.  <span data-ttu-id="46ba7-p116">Erstellen Sie einen Unterordner für jede Sprache, die Sie verwenden. Diese Unterordner enthalten die sprachenspezifischen ADML-Ressourcendateien. Erstellen Sie beispielsweise einen Unterordner für Englisch – USA (EN-US) an folgendem Speicherort:</span><span class="sxs-lookup"><span data-stu-id="46ba7-p116">Create a subfolder for each language that you’ll use. These subfolders will contain the language-specific ADML resource files. For example, create a subfolder for United States English (EN-US) at this location:</span></span>
    
    `%systemroot%\sysvol\domain\policies\PolicyDefinitions\EN-US`

</div>

</div>

<span> </span>

</div>

</div>

</div>

