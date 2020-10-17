---
title: Staging von AV-und OAuth-Zertifikaten mithilfe von-Roll in Set-CsCertificate
description: Bereitstellen von AV-und OAuth-Zertifikaten mithilfe von-Roll in CsCertificate.
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Staging AV and OAuth certificates using -Roll in Set-CsCertificate
ms:assetid: 22dec3cc-4b6b-4df2-b269-5b35df4731a7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ660292(v=OCS.15)
ms:contentKeyID: 49354387
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3732c4adb4327cc1e4111307ab2d72ed080cf221
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48541841"
---
# <a name="staging-av-and-oauth-certificates-in-lync-server-2013-using--roll-in-set-cscertificate"></a><span data-ttu-id="f0529-103">Staging von AV-und OAuth-Zertifikaten in lync Server 2013 using-Roll in Set-CsCertificate</span><span class="sxs-lookup"><span data-stu-id="f0529-103">Staging AV and OAuth certificates in Lync Server 2013 using -Roll in Set-CsCertificate</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f0529-104">_**Letztes Änderungsstand des Themas:** 2012-11-13_</span><span class="sxs-lookup"><span data-stu-id="f0529-104">_**Topic Last Modified:** 2012-11-13_</span></span>

<span data-ttu-id="f0529-105">Die Kommunikation zwischen Audio und Video (a/V) ist eine wichtige Komponente von Microsoft lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="f0529-105">Audio/Video (A/V) communications is a key component of Microsoft Lync Server 2013.</span></span> <span data-ttu-id="f0529-106">Features wie Anwendungsfreigabe und Audio-und Videokonferenzen basieren auf den Zertifikaten, die dem A/V-Edgedienst zugewiesen sind, insbesondere dem A/V-Authentifizierungsdienst.</span><span class="sxs-lookup"><span data-stu-id="f0529-106">Features such as application sharing and audio and video conferencing rely on the certificates assigned to the A/V Edge service, specifically the A/V Authentication service.</span></span>

<div>


> [!IMPORTANT]
> <OL>
> <LI>
> <P><span data-ttu-id="f0529-107">Dieses neue Feature wurde für die A/V-Edgedienst und das <EM>OAuthTokenIssuer</EM> -Zertifikat entwickelt.</span><span class="sxs-lookup"><span data-stu-id="f0529-107">This new feature is designed to work for the A/V Edge service and the <EM>OAuthTokenIssuer</EM> certificate.</span></span> <span data-ttu-id="f0529-108">Andere Zertifikattypen können zusammen mit dem A/V-Edgedienst-und OAuth-Zertifikattyp bereitgestellt werden, profitieren jedoch nicht von dem Verhalten der Koexistenz, das das A/V-Edgedienst Zertifikat enthält.</span><span class="sxs-lookup"><span data-stu-id="f0529-108">Other certificate types can be provisioned along with the A/V Edge service and OAuth certificate type, but will not benefit from the coexistence behavior that the A/V Edge service certificate will.</span></span></P>
> <LI>
> <P><span data-ttu-id="f0529-109">Die lync Server-Verwaltungsshell PowerShell-Cmdlets, mit denen Microsoft lync Server 2013 Zertifikate verwaltet werden, bezieht sich auf das A/V-Edgedienst Zertifikat als <EM>AudioVideoAuthentication</EM> -Zertifikattyp und das OAuthServer-Zertifikat als Typ <EM>OAuthTokenIssuer</EM>.</span><span class="sxs-lookup"><span data-stu-id="f0529-109">The Lync Server Management Shell PowerShell cmdlets used to manage Microsoft Lync Server 2013 certificates refers to the A/V Edge service certificate as the <EM>AudioVideoAuthentication</EM> certificate type and the OAuthServer certificate as type <EM>OAuthTokenIssuer</EM>.</span></span> <span data-ttu-id="f0529-110">Für den Rest dieses Themas und zur eindeutigen Identifizierung der Zertifikate werden diese von demselben Bezeichnertyp, <EM>AudioVideoAuthentication</EM> und <EM>OAuthTokenIssuer</EM>, referenziert.</span><span class="sxs-lookup"><span data-stu-id="f0529-110">For the rest of this topic and to uniquely identify the certificates, they will be referred to by the same identifier type, <EM>AudioVideoAuthentication</EM> and <EM>OAuthTokenIssuer</EM>.</span></span></P></LI></OL>



</div>

<span data-ttu-id="f0529-111">Der a/v-Authentifizierungsdienst ist für die Ausstellung von Token verantwortlich, die von Clients und anderen a/v-Consumern verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="f0529-111">The A/V Authentication service is responsible for issuing tokens that are used by clients and other A/V consumers.</span></span> <span data-ttu-id="f0529-112">Die Token werden aus Attributen auf dem Zertifikat generiert, und wenn das Zertifikat abläuft, resultieren Verbindungsverlust und Anforderung zum erneuten Beitritt mit einem neuen Token, das vom neuen Zertifikat generiert wird.</span><span class="sxs-lookup"><span data-stu-id="f0529-112">The tokens are generated from attributes on the certificate, and when the certificate expires, loss of connection and requirement to rejoin with a new token generated by the new certificate will result.</span></span> <span data-ttu-id="f0529-113">Durch ein neues Feature in lync Server 2013 wird dieses Problem behoben – die Möglichkeit, ein neues Zertifikat im Vorfeld des alten zu inszenieren und zu ermöglichen, dass beide Zertifikate für einen bestimmten Zeitraum weiterhin funktionsfähig sind.</span><span class="sxs-lookup"><span data-stu-id="f0529-113">A new feature in Lync Server 2013 will alleviate this problem – the ability to stage a new certificate in advance of the old one expiring and allowing both certificates to continue to function for a period of time.</span></span> <span data-ttu-id="f0529-114">Dieses Feature verwendet aktualisierte Funktionen im Cmdlet Set-CsCertificate lync Server-Verwaltungsshell.</span><span class="sxs-lookup"><span data-stu-id="f0529-114">This feature uses updated functionality in the Set-CsCertificate Lync Server Management Shell cmdlet.</span></span> <span data-ttu-id="f0529-115">Der neue Parameter – Roll mit dem vorhandenen Parameter – EffectiveDate ", platziert das neue AudioVideoAuthentication-Zertifikat im Zertifikatspeicher.</span><span class="sxs-lookup"><span data-stu-id="f0529-115">The new parameter –Roll, with the existing parameter –EffectiveDate, will place the new AudioVideoAuthentication certificate in the certificate store.</span></span> <span data-ttu-id="f0529-116">Das ältere AudioVideoAuthentication-Zertifikat bleibt weiterhin für ausgestellte Token erhalten, für die validiert werden soll.</span><span class="sxs-lookup"><span data-stu-id="f0529-116">The older AudioVideoAuthentication certificate will still remain for issued tokens to be validated against.</span></span> <span data-ttu-id="f0529-117">Beginnend mit dem Setzen des neuen AudioVideoAuthentication-Zertifikats wird die folgende Reihe von Ereignissen ausgeführt:</span><span class="sxs-lookup"><span data-stu-id="f0529-117">Beginning with putting the new AudioVideoAuthentication certificate in place, the following series of events will occur:</span></span>

<div>


> [!TIP]
> <span data-ttu-id="f0529-118">Mithilfe der lync Server-Verwaltungsshell-Cmdlets zum Verwalten von Zertifikaten können Sie separate und unterschiedliche Zertifikate für jeden Zweck auf dem Edgeserver anfordern.</span><span class="sxs-lookup"><span data-stu-id="f0529-118">Using the Lync Server Management Shell cmdlets for managing certificates, you can request separate and distinct certificates for each purpose on the Edge Server.</span></span> <span data-ttu-id="f0529-119">Die Verwendung des Zertifikat-Assistenten im lync Server Bereitstellungs-Assistenten unterstützt Sie beim Erstellen von Zertifikaten, ist in der Regel jedoch der <STRONG>Standardtyp</STRONG> , bei dem alle Zertifikat Verwendungen für das Edgeserver auf ein einzelnes Zertifikat verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="f0529-119">Using the Certificate Wizard in the Lync Server Deployment Wizard assists you in creating certificates, but is typically of the <STRONG>default</STRONG> type which couples all certificate uses for the Edge Server onto a single certificate.</span></span> <span data-ttu-id="f0529-120">Die empfohlene Vorgehensweise bei der Verwendung des Features für das parallele Zertifikat besteht darin, das AudioVideoAuthentication-Zertifikat von den anderen Zertifikats Zwecken zu entkoppeln.</span><span class="sxs-lookup"><span data-stu-id="f0529-120">The recommended practice if you are going to use the rolling certificate feature is to decouple the AudioVideoAuthentication certificate from the other certificate purposes.</span></span> <span data-ttu-id="f0529-121">Sie können ein Zertifikat des Standardtyps bereitstellen und inszenieren, aber nur der AudioVideoAuthentication-Teil des kombinierten Zertifikats profitiert von der stagingfunktion.</span><span class="sxs-lookup"><span data-stu-id="f0529-121">You can provision and stage a certificate of the Default type, but only the AudioVideoAuthentication portion of the combined certificate will benefit from the staging.</span></span> <span data-ttu-id="f0529-122">Ein Benutzer, der an einer (beispielsweise) Chatnachrichten Unterhaltung beteiligt ist, wenn das Zertifikat abläuft, muss sich abmelden und wieder anmelden, um das dem Zugriffs-Edgedienst zugeordnete neue Zertifikat verwenden zu können.</span><span class="sxs-lookup"><span data-stu-id="f0529-122">A user involved in (for example) an instant messaging conversation when the certificate expires will need to log out and log back in to make use of the new certificate associated with the Access Edge service.</span></span> <span data-ttu-id="f0529-123">Ein ähnliches Verhalten tritt für einen Benutzer auf, der an einer Webkonferenz beteiligt ist, indem Sie das Webkonferenz-Edgedienst verwenden.</span><span class="sxs-lookup"><span data-stu-id="f0529-123">Similar behavior will occur for a user involved in a Web conference using the Web Conferencing Edge service.</span></span> <span data-ttu-id="f0529-124">Das OAuthTokenIssuer-Zertifikat ist ein bestimmter Typ, der für alle Server freigegeben ist.</span><span class="sxs-lookup"><span data-stu-id="f0529-124">The OAuthTokenIssuer certificate is a specific type that is shared across all servers.</span></span> <span data-ttu-id="f0529-125">Sie erstellen und verwalten das Zertifikat an einer einzigen Stelle, und das Zertifikat wird im zentralen Verwaltungsspeicher für alle anderen Server gespeichert.</span><span class="sxs-lookup"><span data-stu-id="f0529-125">You create and manage the certificate in one place and the certificate is stored in the Central Management store for all other servers.</span></span>



</div>

<span data-ttu-id="f0529-126">Zusätzliche Informationen werden benötigt, um die Optionen und Anforderungen bei der Verwendung des Set-CsCertificate-Cmdlet zum Bereitstellen von Zertifikaten vor dem Ablauf des aktuellen Zertifikats nachvollziehen zu können.</span><span class="sxs-lookup"><span data-stu-id="f0529-126">Additional detail is needed to fully understand your options and requirements when using the Set-CsCertificate cmdlet and using it to stage certificates prior to the current certificate expiring.</span></span> <span data-ttu-id="f0529-127">Der Parameter "–Roll" ist wichtig, dient jedoch nur einem Zweck.</span><span class="sxs-lookup"><span data-stu-id="f0529-127">The –Roll parameter is important, but essentially single purpose.</span></span> <span data-ttu-id="f0529-128">Wenn Sie es als Parameter definieren, sagen Sie Set-CsCertificate, dass Sie Informationen zu dem Zertifikat bereitstellen, das von – Type (beispielsweise AudioVideoAuthentication und OAuthTokenIssuer) betroffen sein wird, wenn das Zertifikat durch – EffectiveDate "definiert wird.</span><span class="sxs-lookup"><span data-stu-id="f0529-128">If you define it as a parameter, you are telling Set-CsCertificate that you will be providing information about the certificate that will be affected defined by –Type (for example AudioVideoAuthentication and OAuthTokenIssuer), when the certificate will become effective defined by –EffectiveDate.</span></span>

<span data-ttu-id="f0529-129">**-Roll:** Der-Roll-Parameter ist erforderlich und enthält Abhängigkeiten, die zusammen mit ihm angegeben werden müssen.</span><span class="sxs-lookup"><span data-stu-id="f0529-129">**-Roll:** The –Roll parameter is required and has dependencies that must be supplied along with it.</span></span> <span data-ttu-id="f0529-130">Parameter, die zum Festlegen der betroffenen Zertifikate und ihrer Anwendungsweise erforderlich sind:</span><span class="sxs-lookup"><span data-stu-id="f0529-130">Required parameters to fully define which certificates will be affected and how they will be applied:</span></span>

<span data-ttu-id="f0529-131">**-EffectiveDate ":** Der Parameter – EffectiveDate "definiert, wann das neue Zertifikat zusammen mit dem aktuellen Zertifikat Co-aktiv werden soll.</span><span class="sxs-lookup"><span data-stu-id="f0529-131">**-EffectiveDate:** The parameter –EffectiveDate defines when the new certificate will become co-active with the current certificate.</span></span> <span data-ttu-id="f0529-132">Die – EffectiveDate "kann nahe der Ablaufzeit des aktuellen Zertifikats liegen, oder es kann einen längeren Zeitraum dauern.</span><span class="sxs-lookup"><span data-stu-id="f0529-132">The –EffectiveDate can be close to the expiry time of the current certificate, or it can be a longer period of time.</span></span> <span data-ttu-id="f0529-133">Ein empfohlenes Minimum – EffectiveDate "für das AudioVideoAuthentication-Zertifikat wäre 8 Stunden, was die Standard Gültigkeitsdauer des Tokens für AV-Edgedienst-Token ist, die mit dem AudioVideoAuthentication-Zertifikat ausgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="f0529-133">A recommended minimum –EffectiveDate for the AudioVideoAuthentication certificate would be 8 hours, which is the default token lifetime for AV Edge service tokens issued using the AudioVideoAuthentication certificate.</span></span>

<span data-ttu-id="f0529-p109">Für das Bereitstellen der OAuthTokenIssuer-Zertifikate liegen verschiedene Anforderungen für die Durchlaufzeit vor, bevor das Zertifikat wirksam werden kann. Der Mindestwert des OAuthTokenIssuer-Zertifikats für die Durchlaufzeit sollte 24 Stunden vor der Ablaufzeit des aktuellen Zertifikats betragen. Die erweiterte Durchlaufzeit für die Koexistenz ist durch andere Serverrollen begründet, die von dem OAuthTokenIssuer-Zertifikat (beispielsweise Exchange Server) abhängen, das eine längere Aufbewahrungszeit für durch Zertifikate erstellte Authentifizierungs- und Verschlüsselungsschlüsselelemente besitzt.</span><span class="sxs-lookup"><span data-stu-id="f0529-p109">When staging OAuthTokenIssuer certificates, there are different requirements for the lead time before the certificate can become effective. The minimum time that the OAuthTokenIssuer certificate should have for its lead time is 24 hours before the expiration time of the current certificate. The extended lead time for the coexistence is because of other server roles that are dependent on the OAuthTokenIssuer certificate (Exchange Server, for example) which has a longer retention time for certificate created authentication and encryption key materials.</span></span>

<span data-ttu-id="f0529-137">**-Fingerabdruck:** Bei dem Fingerabdruck handelt es sich um ein Attribut des Zertifikats, das für dieses Zertifikat eindeutig ist.</span><span class="sxs-lookup"><span data-stu-id="f0529-137">**-Thumbprint:** The thumbprint is an attribute on the certificate that is unique to that certificate.</span></span> <span data-ttu-id="f0529-138">Mit dem Parameter "–Thumbprint" wir das Zertifikat ermittelt, das von den Aktionen des Cmdlets "Set-CsCertificate" betroffen ist.</span><span class="sxs-lookup"><span data-stu-id="f0529-138">The –Thumbprint parameter is used to identify the certificate that will be affected by the actions of the Set-CsCertificate cmdlet.</span></span>

<span data-ttu-id="f0529-139">**-Geben Sie Folgendes ein:** Der Parameter – Type kann einen einzelnen Zertifikat Verwendungstyp oder eine durch trennzeichengetrennte Liste mit Zertifikat Verwendungstypen akzeptieren.</span><span class="sxs-lookup"><span data-stu-id="f0529-139">**-Type:** The –Type parameter can accept a single certificate usage type or a comma separated list of certificate usage types.</span></span> <span data-ttu-id="f0529-140">Die Zertifikattypen geben für das Cmdlet und den Server an, worin der Zweck des Zertifikats besteht.</span><span class="sxs-lookup"><span data-stu-id="f0529-140">The certificate types are those that identify to the cmdlet and to the server what the purpose of the certificate is.</span></span> <span data-ttu-id="f0529-141">Geben Sie beispielsweise AudioVideoAuthentication für die Verwendung durch den A/V-Edgedienst und den AV-Authentifizierungsdienst ein.</span><span class="sxs-lookup"><span data-stu-id="f0529-141">For example, type AudioVideoAuthentication is for use by the A/V Edge service and the AV Authentication service.</span></span> <span data-ttu-id="f0529-142">Wenn Sie verschiedene Zertifikattypen zum gleichen Zeitpunkt bereitstellen möchten, müssen Sie die längste effektive Mindestdurchlaufzeit für die Zertifikate berücksichtigen.</span><span class="sxs-lookup"><span data-stu-id="f0529-142">If you decide to stage and provision certificates of a different type at the same time, you must consider the longest required minimum effective lead time for the certificates.</span></span> <span data-ttu-id="f0529-143">Sie müssen beispielsweise Zertifikate vom Typ "AudioVideoAuthentication" und Typ "OAuthTokenIssuer" bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="f0529-143">For example, you need to stage certificates of type AudioVideoAuthentication and OAuthTokenIssuer.</span></span> <span data-ttu-id="f0529-144">Als Mindestwert muss für "–EffectiveDate" der höhere Wert der beiden Zertifikate festgelegt werden, in diesem Fall der Wert des Zertifikats "OAuthTokenIssuer", dessen Mindestdurchlaufzeit 24 Stunden beträgt.</span><span class="sxs-lookup"><span data-stu-id="f0529-144">Your minimum –EffectiveDate must be the greater of the two certificates, in this case the OAuthTokenIssuer, which has a minimum lead time of 24 hours.</span></span> <span data-ttu-id="f0529-145">Wenn Sie das Zertifikat "AudioVideoAuthentication" nicht mit einer Durchlaufzeit von 24 Stunden bereitstellen möchten, stellen Sie es separat mit einem Ihren Anforderungen entsprechenden Wert für "EffectiveDate" bereit.</span><span class="sxs-lookup"><span data-stu-id="f0529-145">If you do not want to stage the AudioVideoAuthentication certificate with a lead time of 24 hours, stage it separately with an EffectiveDate that is more to your requirements.</span></span>

<div>

## <a name="to-update-or-renew-an-av-edge-service-certificate-with-a-roll-and--effectivedate-parameters"></a><span data-ttu-id="f0529-146">So aktualisieren oder erneuern Sie ein A/V-Edgedienst-Zertifikat mit den Parametern "– Roll" und "-EffectiveDate" "</span><span class="sxs-lookup"><span data-stu-id="f0529-146">To update or renew an A/V Edge service certificate with a –Roll and -EffectiveDate parameters</span></span>

1.  <span data-ttu-id="f0529-147">Melden Sie sich beim lokalen Computer als Mitglied der Gruppe Administratoren an.</span><span class="sxs-lookup"><span data-stu-id="f0529-147">Log on to the local computer as a member of the Administrators group.</span></span>

2.  <span data-ttu-id="f0529-148">Fordern Sie ein Erneuerungs-oder neues AudioVideoAuthentication-Zertifikat mit exportier barem privaten Schlüssel für das vorhandene Zertifikat im A/V-Edgedienst an.</span><span class="sxs-lookup"><span data-stu-id="f0529-148">Request a renewal or new AudioVideoAuthentication certificate with exportable private key for the existing certificate on the A/V Edge service.</span></span>

3.  <span data-ttu-id="f0529-149">Importieren Sie das neue AudioVideoAuthentication-Zertifikat in den Edgeserver und alle anderen Edgeserver in Ihrem Pool (sofern ein Pool bereitgestellt wurde).</span><span class="sxs-lookup"><span data-stu-id="f0529-149">Import the new AudioVideoAuthentication certificate to the Edge Server and all other Edge Server in your pool (if you have a pool deployed).</span></span>

4.  <span data-ttu-id="f0529-150">Konfigurieren Sie das importierte Zertifikat mit dem Cmdlet "Set-CsCertificate", und verwenden Sie den Parameter "–Roll" mit dem Parameter "–EffectiveDate".</span><span class="sxs-lookup"><span data-stu-id="f0529-150">Configure the imported certificate with the Set-CsCertificate cmdlet and use the –Roll parameter with the –EffectiveDate parameter.</span></span> <span data-ttu-id="f0529-151">Das Gültigkeitsdatum sollte als Ablaufzeit des aktuellen Zertifikats (14:00:00 Uhr) minus Tokengültigkeitsdauer (standardmäßig acht Stunden) festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="f0529-151">The effective date should be defined as the current certificate expire time (14:00:00, or 2:00:00 PM) minus token lifetime (by default eight hours).</span></span> <span data-ttu-id="f0529-152">Dies gibt uns eine Zeit, für die das Zertifikat auf aktiv festgelegt werden muss, und ist der-EffectiveDate " \<string\> :" 7/22/2012 6:00:00 am ".</span><span class="sxs-lookup"><span data-stu-id="f0529-152">This gives us a time that the certificate must be set to active, and is the –EffectiveDate \<string\>: “7/22/2012 6:00:00 AM”.</span></span>
    
    <div>
    

    > [!IMPORTANT]
    > <span data-ttu-id="f0529-153">Für eine Edgepool müssen Sie alle AudioVideoAuthentication-Zertifikate bereitstellen und mit dem Datum und der Uhrzeit bereitstellen, die durch den Parameter – EffectiveDate "des ersten bereitgestellten Zertifikats definiert wurden, um mögliche A/V-KOMMUNIKATIONSUNTERBRECHUNGEN zu vermeiden, da das ältere Zertifikat abläuft, bevor alle Client-und Consumer-Token mithilfe des neuen Zertifikats erneuert wurden.</span><span class="sxs-lookup"><span data-stu-id="f0529-153">For an Edge pool, you must have all AudioVideoAuthentication certificates deployed and provisioned by the date and time defined by the –EffectiveDate parameter of the first certificate deployed to avoid possible A/V communications disruption due to the older certificate expiring before all client and consumer tokens have been renewed using the new certificate.</span></span>

    
    </div>
    
    <span data-ttu-id="f0529-154">Der Befehl "Set-CsCertificate" mit den Parametern "–Roll" und "–EffectiveTime":</span><span class="sxs-lookup"><span data-stu-id="f0529-154">The Set-CsCertificate command with the –Roll and –EffectiveTime parameter:</span></span>
    
        Set-CsCertificate -Type AudioVideoAuthentication -Thumbprint <thumb print of new certificate> -Roll -EffectiveDate <date and time for certificate to become active>
    
    <span data-ttu-id="f0529-155">Ein Set-CsCertificate-Beispielbefehl:</span><span class="sxs-lookup"><span data-stu-id="f0529-155">An example Set-CsCertificate command:</span></span>
    
        Set-CsCertificate -Type AudioVideoAuthentication -Thumbprint "B142918E463981A76503828BB1278391B716280987B" -Roll -EffectiveDate "7/22/2012 6:00:00 AM"
    
    <div>
    

    > [!IMPORTANT]
    > <span data-ttu-id="f0529-p113">Das Gültigkeitsdatum muss so formatiert werden, dass es den Regions- und Spracheinstellungen Ihres Servers entspricht. Im Beispiel werden die englischen (USA) Regions- und Spracheinstellungen verwendet.</span><span class="sxs-lookup"><span data-stu-id="f0529-p113">The EffectiveDate must be formatted to match your server’s region and language settings. The example uses the US English Region and Language settings</span></span>

    
    </div>

<span data-ttu-id="f0529-158">Mit einer optischen Zeitachse können Sie den besser verstehen, der von "Set-CsCertificate", "-Roll" und "–EffectiveDate" zum Bereitstellen eines neuen Zertifikats für die Aussstellung neuer AudioVideoAuthentication-Token verwendet wird, während weiterhin mit einem vorhandenen Zertifikat das von Benutzern verwendete AudioVideoAuthentication-Zertifikat validiert wird.</span><span class="sxs-lookup"><span data-stu-id="f0529-158">To further understand the process that Set-CsCertificate, -Roll, and –EffectiveDate use to stage a new certificate for issuing new AudioVideoAuthentication tokens while still using an existing certificate to validate AudioVideoAuthentication that are in use by consumers, a visual timeline is an effective means of understanding the process.</span></span>

<span data-ttu-id="f0529-159">Im folgenden Beispiel bestimmt der Administrator, dass das A/V-Edgedienst Zertifikat um 2:00:00 Uhr am 07/22/2012 abläuft.</span><span class="sxs-lookup"><span data-stu-id="f0529-159">In the following example, the administrator determines that the A/V Edge service certificate is due to expire at 2:00:00 PM on 07/22/2012.</span></span> <span data-ttu-id="f0529-160">Er fordert und empfängt ein neues Zertifikat und importiert es in jeden Edgeserver in seinem Pool.</span><span class="sxs-lookup"><span data-stu-id="f0529-160">He requests and receives a new certificate and imports it to each Edge Server in his pool.</span></span> <span data-ttu-id="f0529-161">Am 22.07.2012 um 14 Uhr startet er die Ausführung von "Get-CsCertificate" mit "–Roll", "-Thumbprint" (dieser Wert entspricht der Fingerabdruckzeichenfolge des neuen Zertifikats) und "–EffectiveTime" (für diesen Wert ist 22.07.2012 6:00:00 Uhr festgelegt).</span><span class="sxs-lookup"><span data-stu-id="f0529-161">At 2 AM on 07/22/2012, he begins running Get-CsCertificate with –Roll, -Thumbprint equal to the thumbprint string of the new certificate, and –EffectiveTime set to 07/22/2012 6:00:00 AM.</span></span> <span data-ttu-id="f0529-162">Er führt diesen Befehl für jede Edgeserver aus.</span><span class="sxs-lookup"><span data-stu-id="f0529-162">He runs this command on each Edge Server.</span></span>

<span data-ttu-id="f0529-163">![Verwenden der Parameter "Roll" und "EffectiveDate" ".](images/JJ660292.21d51a76-0d03-4ed7-a37e-a7c14940265f(OCS.15).jpg "Verwenden der Parameter "Roll" und "EffectiveDate" ".")</span><span class="sxs-lookup"><span data-stu-id="f0529-163">![Using the Roll and the EffectiveDate parameters.](images/JJ660292.21d51a76-0d03-4ed7-a37e-a7c14940265f(OCS.15).jpg "Using the Roll and the EffectiveDate parameters.")</span></span>

<span data-ttu-id="f0529-p115">Wird das Gültigkeitsdatum (22.07.2012 6:00:00 Uhr) erreicht, werden alle neuen Token vom neuen Zertifikat ausgestellt. Bei der Validierung von Token werden die Token zunächst anhand des neuen Zertifikats überprüft. Schlägt die Überprüfung fehl, wird das alte Zertifikat verwendet. Die Vorgehensweise, erst das neue und anschließend das alte Zertifikat zu verwenden, wird bis zur Ablaufzeit des alten Zertifikats fortgesetzt. Sobald das alte Zertifikat abgelaufen ist (22.07.2012 14:00:00 Uhr), werden Token nur durch das neue Zertifikat überprüft. Das alte Zertifikat kann mithilfe des Cmdlets "Remove-CsCertificate" mit dem Parameter "–Previous" sicher entfernt werden.</span><span class="sxs-lookup"><span data-stu-id="f0529-p115">When the effective time is reached (7/22/2012 6:00:00 AM), all new tokens are issued by the new certificate. When validating tokens, tokens will first be validated against the new certificate. If the validation fails, the old certificate is tried. The process of trying the new and falling back to the old certificate will continue until the expiry time of the old certificate. Once the old certificate has expired (7/22/2012 2:00:00 PM), tokens will only be validated by the new certificate. The old certificate can be safely removed using the Remove-CsCertificate cmdlet with the –Previous parameter.</span></span>

    Remove-CsCertificate -Type AudioVideoAuthentication -Previous

</div>

<div>

## <a name="to-update-or-renew-an-oauthtokenissuer-certificate-with-a-roll-and--effectivedate-parameters"></a><span data-ttu-id="f0529-170">So aktualisieren oder erneuen Sie ein OAuthTokenIssuer-Zertifikat mit den Parametern "–Roll" und "-EffectiveDate"</span><span class="sxs-lookup"><span data-stu-id="f0529-170">To update or renew an OAuthTokenIssuer certificate with a –Roll and -EffectiveDate parameters</span></span>

1.  <span data-ttu-id="f0529-171">Melden Sie sich beim lokalen Computer als Mitglied der Gruppe Administratoren an.</span><span class="sxs-lookup"><span data-stu-id="f0529-171">Log on to the local computer as a member of the Administrators group.</span></span>

2.  <span data-ttu-id="f0529-172">Fordern Sie ein Erneuerungs-oder neues OAuthTokenIssuer-Zertifikat mit exportier barem privaten Schlüssel für das vorhandene Zertifikat im A/V-Edgedienst an.</span><span class="sxs-lookup"><span data-stu-id="f0529-172">Request a renewal or new OAuthTokenIssuer certificate with exportable private key for the existing certificate on the A/V Edge service.</span></span>

3.  <span data-ttu-id="f0529-173">Importieren Sie das neue OAuthTokenIssuer-Zertifikat in einen Front-End-Server in Ihrem Pool (sofern ein Pool bereitgestellt wurde).</span><span class="sxs-lookup"><span data-stu-id="f0529-173">Import the new OAuthTokenIssuer certificate to a Front End Server in your pool (if you have a pool deployed).</span></span> <span data-ttu-id="f0529-174">Das OAuthTokenIssuer-Zertifikat wird global repliziert und muss auf den Servern in Ihrer Bereitstellung aktualisiert und erneuert werden.</span><span class="sxs-lookup"><span data-stu-id="f0529-174">The OAuthTokenIssuer certificate is replicated globally and only needs to be updated and renewed at any server in your deployment.</span></span> <span data-ttu-id="f0529-175">Die Front-End-Server wird als Beispiel verwendet.</span><span class="sxs-lookup"><span data-stu-id="f0529-175">The Front End Server is used as an example.</span></span>

4.  <span data-ttu-id="f0529-p117">Konfigurieren Sie das importierte Zertifikat mit dem Cmdlet "Set-CsCertificate", und verwenden Sie den Parameter "–Roll" mit dem Parameter "–EffectiveDate". Das Gültigkeitsdatum sollte als Ablaufzeit des aktuellen Zertifikats (14:00:00 Uhr) minus Tokengültigkeitsdauer (standardmäßig acht Stunden) festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="f0529-p117">Configure the imported certificate with the Set-CsCertificate cmdlet and use the –Roll parameter with the –EffectiveDate parameter. The effective date should be defined as the current certificate expire time (14:00:00, or 2:00:00 PM) minus a minimum of 24 hours.</span></span>
    
    <span data-ttu-id="f0529-178">Der Befehl "Set-CsCertificate" mit den Parametern "–Roll" und "–EffectiveTime":</span><span class="sxs-lookup"><span data-stu-id="f0529-178">The Set-CsCertificate command with the –Roll and –EffectiveTime parameter:</span></span>
    
        Set-CsCertificate -Type OAuthTokenIssuer -Thumbprint <thumb print of new certificate> -Roll -EffectiveDate <date and time for certificate to become active>
    
    <span data-ttu-id="f0529-179">Ein Set-CsCertificate-Beispielbefehl:</span><span class="sxs-lookup"><span data-stu-id="f0529-179">An example Set-CsCertificate command:</span></span>
    
        Set-CsCertificate -Type OAuthTokenIssuer -Thumbprint "B142918E463981A76503828BB1278391B716280987B" -Roll -EffectiveDate "7/21/2012 1:00:00 PM"
    
    <div>
    

    > [!IMPORTANT]
    > <span data-ttu-id="f0529-p118">Das Gültigkeitsdatum muss so formatiert werden, dass es den Regions- und Spracheinstellungen Ihres Servers entspricht. Im Beispiel werden die englischen (USA) Regions- und Spracheinstellungen verwendet.</span><span class="sxs-lookup"><span data-stu-id="f0529-p118">The EffectiveDate must be formatted to match your server’s region and language settings. The example uses the US English Region and Language settings</span></span>

    
    </div>

<span data-ttu-id="f0529-p119">Wird das Gültigkeitsdatum (21.07.2012 01:00:00 Uhr) erreicht, werden alle neuen Token vom neuen Zertifikat ausgestellt. Bei der Validierung von Token werden die Token zunächst anhand des neuen Zertifikats überprüft. Schlägt die Überprüfung fehl, wird das alte Zertifikat verwendet. Die Vorgehensweise, erst das neue und anschließend das alte Zertifikat zu verwenden, wird bis zur Ablaufzeit des alten Zertifikats fortgesetzt. Sobald das alte Zertifikat abgelaufen ist (22.07.2012 14:00:00 Uhr), werden Token nur durch das neue Zertifikat überprüft. Das alte Zertifikat kann mithilfe des Cmdlets "Remove-CsCertificate" mit dem Parameter "–Previous" sicher entfernt werden.</span><span class="sxs-lookup"><span data-stu-id="f0529-p119">When the effective time is reached (7/21/2012 1:00:00 AM), all new tokens are issued by the new certificate. When validating tokens, tokens will first be validated against the new certificate. If the validation fails, the old certificate is tried. The process of trying the new and falling back to the old certificate will continue until the expiry time of the old certificate. Once the old certificate has expired (7/22/2012 2:00:00 PM), tokens will only be validated by the new certificate. The old certificate can be safely removed using the Remove-CsCertificate cmdlet with the –Previous parameter.</span></span>

    Remove-CsCertificate -Type OAuthTokenIssuer -Previous

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="f0529-188">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f0529-188">See Also</span></span>


[<span data-ttu-id="f0529-189">Planen von Edgeserver Zertifikaten in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f0529-189">Plan for Edge Server certificates in Lync Server 2013</span></span>](lync-server-2013-plan-for-edge-server-certificates.md)  
[<span data-ttu-id="f0529-190">Verwalten der Server-zu-Server-Authentifizierung (OAuth) und der Partneranwendungen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f0529-190">Managing server-to-server authentication (OAuth) and partner applications in Lync Server 2013</span></span>](lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md)  


[<span data-ttu-id="f0529-191">Einrichten von Edge-Zertifikaten für lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f0529-191">Set up Edge certificates for Lync Server 2013</span></span>](lync-server-2013-set-up-edge-certificates.md)  
<span data-ttu-id="f0529-192">[Gruppe-CsCertificate](https://technet.microsoft.com/library/Gg398518(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="f0529-192">[Set-CsCertificate](https://technet.microsoft.com/library/Gg398518(v=OCS.15))</span></span>  
<span data-ttu-id="f0529-193">[Remove-CsCertificate](https://technet.microsoft.com/library/Gg412895(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="f0529-193">[Remove-CsCertificate](https://technet.microsoft.com/library/Gg412895(v=OCS.15))</span></span>  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

