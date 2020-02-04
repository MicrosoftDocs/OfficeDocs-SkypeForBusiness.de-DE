---
title: 'Lync Server 2013: Zertifikats Zusammenfassung – Extensible Messaging and Presence Protocol (XMPP) Federation'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Certificate summary - Extensible messaging and presence protocol (XMPP) federation
ms:assetid: b059a34e-99df-40af-91fe-fe2aa52841f6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ618374(v=OCS.15)
ms:contentKeyID: 49105661
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7af2c226397c5225fc26f6dbdf40d12a4bdb1ca0
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41736625"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="certificate-summary---extensible-messaging-and-presence-protocol-xmpp-federation-in-lync-server-2013"></a><span data-ttu-id="ff550-102">Zertifikatzusammenfassung – Extensible Messaging and Presence Protocol (XMPP) Federation in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ff550-102">Certificate summary - Extensible messaging and presence protocol (XMPP) federation in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ff550-103">_**Letztes Änderungsdatum des Themas:** 2012-12-23_</span><span class="sxs-lookup"><span data-stu-id="ff550-103">_**Topic Last Modified:** 2012-12-23_</span></span>

<span data-ttu-id="ff550-104">Für die Zertifikatanforderungen für die Aktivierung und Einrichtung der Kommunikation mit dem Extensible Messaging and Presence Protocol (XMPP)-Partner ist die zusätzliche Aufzeichnung ihrer XMPP-Domänen erforderlich.</span><span class="sxs-lookup"><span data-stu-id="ff550-104">Certificate requirements for enabling and establishing communications with extensible messaging and presence protocol (XMPP) partners require the additional record of your XMPP domains.</span></span> <span data-ttu-id="ff550-105">Der Datensatz, der im Zertifikat als alternativer Betreff (Subject Alternative Name, San) enthalten ist, ist die Domäne, die an der XMPP-Kommunikation teilnehmen kann.</span><span class="sxs-lookup"><span data-stu-id="ff550-105">The record that is included on the certificate as a subject alternative name (SAN) will be the domain that can participate in XMPP communications.</span></span> <span data-ttu-id="ff550-106">Bei der Domäne kann es sich um die Domäne auf Stammebene (beispielsweise contoso.com) handeln, wenn Sie XMPP für Ihre gesamte Domäne aktivieren möchten oder untergeordnete Domänen (beispielsweise Corp.contoso.com, Finance.contoso.com) ausgewählt werden können, wenn Sie XMPP für eine Teilmenge der Benutzer aktivieren.</span><span class="sxs-lookup"><span data-stu-id="ff550-106">The domain can be the root-level domain (for example, contoso.com) if you want to enable XMPP for your entire domain, or can be selected child domains (for example, corp.contoso.com, finance.contoso.com) if you are enabling XMPP for a subset of users.</span></span>

<div>

## <a name="certificate-summary-for-extensible-messaging-and-presence-protocol"></a><span data-ttu-id="ff550-107">Zertifikatzusammenfassung für erweiterbares Messaging und Anwesenheits Protokoll</span><span class="sxs-lookup"><span data-stu-id="ff550-107">Certificate Summary for Extensible Messaging and Presence Protocol</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ff550-108">Komponente</span><span class="sxs-lookup"><span data-stu-id="ff550-108">Component</span></span></th>
<th><span data-ttu-id="ff550-109">Name des Antragstellers</span><span class="sxs-lookup"><span data-stu-id="ff550-109">Subject name</span></span></th>
<th><span data-ttu-id="ff550-110">Subject Alternative Names (San)/Order</span><span class="sxs-lookup"><span data-stu-id="ff550-110">Subject alternative names (SAN)/Order</span></span></th>
<th><span data-ttu-id="ff550-111">Kommentare</span><span class="sxs-lookup"><span data-stu-id="ff550-111">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ff550-112">Zuweisen des Zugriffs-Edgedienst des Edge-Servers oder Edge-Pools</span><span class="sxs-lookup"><span data-stu-id="ff550-112">Assign to Access Edge service of Edge Server or Edge pool</span></span></p></td>
<td><p><span data-ttu-id="ff550-113">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="ff550-113">sip.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="ff550-114">webcon.contoso.com</span><span class="sxs-lookup"><span data-stu-id="ff550-114">webcon.contoso.com</span></span></p>
<p><span data-ttu-id="ff550-115">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="ff550-115">sip.contoso.com</span></span></p>
<p><span data-ttu-id="ff550-116">sip.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="ff550-116">sip.fabrikam.com</span></span></p>
<p><span data-ttu-id="ff550-117">contoso.com</span><span class="sxs-lookup"><span data-stu-id="ff550-117">contoso.com</span></span></p></td>
<td><p><span data-ttu-id="ff550-118">Die ersten drei San-Einträge sind die normalen San-Einträge für einen Full Edge-Server.</span><span class="sxs-lookup"><span data-stu-id="ff550-118">The first three SAN entries are the normal SAN entries for a full Edge Server.</span></span> <span data-ttu-id="ff550-119">Der contoso.com ist der Eintrag, der für den Verbund mit dem XMPP-Partner auf der Stammdomänen Ebene erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="ff550-119">The contoso.com is the entry required for federation with the XMPP partner at the root domain level.</span></span> <span data-ttu-id="ff550-120">Dieser Eintrag ermöglicht XMPP für alle Domänen mit dem Suffix contoso.com.</span><span class="sxs-lookup"><span data-stu-id="ff550-120">This entry will allow XMPP for all domains with the suffix contoso.com.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="see-also"></a><span data-ttu-id="ff550-121">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ff550-121">See Also</span></span>


[<span data-ttu-id="ff550-122">Beispiel für eine XMPP-Konfiguration in Lync Server 2013 – XMPP-Partnerverbund mit Google Talk</span><span class="sxs-lookup"><span data-stu-id="ff550-122">Example XMPP configuration in Lync Server 2013 – XMPP federation with Google Talk</span></span>](lync-server-2013-example-xmpp-configuration-–-xmpp-federation-with-google-talk.md)  


[<span data-ttu-id="ff550-123">Planen von Edgeserver-Zertifikaten in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ff550-123">Plan for Edge Server certificates in Lync Server 2013</span></span>](lync-server-2013-plan-for-edge-server-certificates.md)  


[<span data-ttu-id="ff550-124">Einrichten von Edgezertifikaten für Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ff550-124">Set up Edge certificates for Lync Server 2013</span></span>](lync-server-2013-set-up-edge-certificates.md)  
[<span data-ttu-id="ff550-125">Request-CsCertificate</span><span class="sxs-lookup"><span data-stu-id="ff550-125">Request-CsCertificate</span></span>](https://docs.microsoft.com/powershell/module/skype/Request-CsCertificate)  
[<span data-ttu-id="ff550-126">Set-CsCertificate</span><span class="sxs-lookup"><span data-stu-id="ff550-126">Set-CsCertificate</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsCertificate)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

