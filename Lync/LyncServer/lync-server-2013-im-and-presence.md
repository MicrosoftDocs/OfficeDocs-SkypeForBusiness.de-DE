---
title: Lync Server 2013 Chat und Anwesenheit
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: IM and presence
ms:assetid: 6a93ae95-3b64-410b-ab72-74dea232f065
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg417162(v=OCS.15)
ms:contentKeyID: 48184398
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a1c612102cb34113c96d02e9e408563a16bfb3bc
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "42150654"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="im-and-presence-in-lync-server-2013"></a>Chat und Anwesenheitsinformationen in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2013-10-07_

Instant Messaging (Sofortnachrichten) und Anwesenheit werden in jeder lync Server-Bereitstellung automatisch installiert.

*Anwesenheitsinformationen* ermöglichen es Benutzern, Kollegen zum richtigen Zeitpunkt und über den richtigen Kommunikationskanal zu erreichen und erhöhen so die Produktivität in der Arbeitsumgebung. Zu den Anwesenheitsinformationen eines Benutzers gehören Informationen wie Verfügbarkeit, Kommunikationsbereitschaft, weitere Hinweise (z. B. Standort und Status) und Angaben dazu, über welchen Kommunikationskanal der Benutzer erreichbar ist. Präsenz wird in lync Server mit Bildern, Standortinformationen und einem umfangreichen Satz von Anwesenheitsstatus verbessert, der "aus Arbeit", "nicht stören" und "gleich wieder da", zusätzlich zu den grundlegenden Zuständen wie "verfügbar", "beschäftigt" und "in einer Konferenz" umfasst. Administratoren können außerdem benutzerdefinierte, organisationsspezifische Anwesenheitszustände definieren.

Mit der Kontaktverwaltung und den Benutzerzugriffsoptionen können Benutzer steuern, welche Informationen anderen Benutzern angezeigt werden. Benutzer können verschiedene Kontaktebenen festlegen, für die jeweils verschiedene Stufen von Anwesenheitsinformationen angezeigt werden.

Mit einem einfachen Blick auf eine Kontaktliste erhalten Benutzer alle für sie relevanten Informationen. Einfache farbige Symbole weisen auf den Anwesenheitsstatus anderer Benutzer hin, und es werden Bilder und Standorte angezeigt.

Bei der Integration von lync Server und anderen Produkten wie Outlook und SharePoint wird jedes Mal, wenn der Name eines Kontakts angezeigt wird, beispielsweise in einer e-Mail-Nachricht oder auf einer Teamwebsite, auch der Status und die Kontaktinformationen angezeigt. Wenn Sie Exchange 2013 bereitstellen, können lync Server und Exchange 2013 darüber hinaus einen einheitlichen Kontaktspeicher freigeben, auf den von Clients der beiden Produkte zugegriffen werden kann.

Mit Chatnachrichten in lync Server können sich Benutzer schnell und zeitnah informieren. Wenn es Ihnen lieber ist, können Ihre Benutzer auch mit Benutzern öffentlicher Chat Netzwerke wie MSN/Windows Live, Yahoo\!und AOL kommunizieren. Beachten Sie, dass für Verbindungen mit öffentlichen Chat Diensten mit Windows Live, AOL und Yahoo möglicherweise eine separate Lizenz erforderlich ist.\! Lync Server umfasst auch die Kompatibilität mit dem Extensible Messaging and Presence Protocol (XMPP), damit Ihre Benutzer Chatnachrichten und Anwesenheitsinformationen mit Benutzern von XMPP-Diensten wie Google Talk austauschen können.

<div>


> [!IMPORTANT]  
> <UL>
> <LI>
> <P>Seit dem 1. September 2012 ist die Microsoft lync Public Chat Connectivity-Benutzerabonnementlizenz ("PIC USL") nicht mehr für neue oder erneuerte Verträge verfügbar. Kunden mit aktiven Lizenzen können weiterhin mit Yahoo! zusammenarbeiten. Messenger, bis der Dienst das Datum heruntergefahren hat. Ein End-of-Life-Datum vom Juni 2014 für AOL und Yahoo! wurde angekündigt. Ausführliche Informationen finden Sie unter <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Support for Public Instant Messenger Connectivity in lync Server 2013</A>.</P>
> <LI>
> <P>Bei der PIC-USL handelt es sich um eine Abonnementlizenz pro Benutzer pro Monat, die für lync Server oder Office Communications Server für die Zusammensetzung mit Yahoo! erforderlich ist. Messenger. Die Fähigkeit von Microsoft, diesen Dienst bereitzustellen, wurde von der Unterstützung von Yahoo! abhängig gemacht, die zugrunde liegende Vereinbarung, für die die Rückabwicklung erfolgt.</P>
> <LI>
> <P>Lync ist mehr denn je ein leistungsfähiges Tool für die Verbindung zwischen verschiedenen Organisationen und mit Einzelpersonen auf der ganzen Welt. Für den Verbund mit Windows Live Messenger sind keine zusätzlichen Benutzer-/Gerätelizenzen außerhalb der lync-Standard-CAL erforderlich. Skype Federation wird dieser Liste hinzugefügt, sodass lync-Benutzer Hunderte Millionen von Benutzern mit Chat und VoIP erreichen können.</P></LI></UL>



</div>

Anhand der aufgezeichneten Unterhaltungen können Benutzer ihre älteren Sofortnachrichten verfolgen und Informationen abrufen, die möglicherweise Monate zuvor per Sofortnachricht mitgeteilt wurden.

Mit dem Feature für beständigen Chat können Benutzer an mehrteiligen, themenbasierten Unterhaltungen teilnehmen, die im Laufe der Zeit beibehalten werden. In Chatrooms (Diskussionsforen) veröffentlichte Nachrichten können langlebig sein (d. h. dauerhaft verfügbar), sodass Benutzer aus unterschiedlichen Standorten und Abteilungen an dem Chat teilnehmen können, selbst wenn sie nicht alle zum gleichen Zeitpunkt online sind.

Wenn Ihre Organisation rechtliche Vorschriften bezüglich Compliance einhalten muss, können Sie eine Archivierungsfunktion für Nachrichten bereitstellen, um die Inhalte von Sofortnachrichten für alle Benutzer in Ihrer Organisation oder auch nur für bestimmte festgelegte Benutzer zu archivieren. Wenn Sie auch Exchange 2013 bereitstellen, kann Ihr Chat Archiv in das in-situ-Speicherfeature von Exchange integriert werden, um eine einfache Verwaltungserfahrung für ihre Kompatibilität bereitzustellen.

</div>

<span> </span>

</div>

</div>

</div>

