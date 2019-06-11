---
title: 'Lync Server 2013: Chat und Anwesenheit'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: IM and presence
ms:assetid: 6a93ae95-3b64-410b-ab72-74dea232f065
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg417162(v=OCS.15)
ms:contentKeyID: 48184398
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 18eb3d4a7fa5daaa59817d2eefde7af3a8e3f494
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34832037"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="im-and-presence-in-lync-server-2013"></a>Chat und Anwesenheit in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2013-10-07_

Instant Messaging (im) und Anwesenheit werden in jeder lync Server-Bereitstellung automatisch installiert.

** Mit Anwesenheitsinformationen können Benutzer sich zur richtigen Zeit mit der richtigen Kommunikationsform an Kollegen wenden und so zu einer produktiveren Arbeitsumgebung führen. Die Anwesenheit eines Benutzers ist eine Sammlung von Informationen, die Verfügbarkeit, Kommunikationsbereitschaft, zusätzliche Notizen (wie Standort und Status) sowie die Art und Weise, wie der Benutzer kontaktiert werden kann. Der Anwesenheitsstatus wird in lync Server mit Bildern, Standortinformationen und einem umfangreichen Satz an Anwesenheitsstatus verbessert, in dem "aus Arbeit", "nicht stören" und "gleich zurück", zusätzlich zu den grundlegenden Zuständen wie "verfügbar", "beschäftigt" und "in einer Konferenz" enthalten sind. Administratoren können auch benutzerdefinierte, organisationsspezifische Anwesenheitsstatus definieren.

Mit den Optionen für die Kontaktverwaltung und den Benutzer Zugriff können Benutzer steuern, welche Informationen andere Personen sehen können. Benutzer können unterschiedliche Ebenen von Kontakten einrichten, die jeweils unterschiedliche Ebenen von Anwesenheitsinformationen anzeigen können.

Wenn Sie sich einfach eine Kontaktliste ansehen, können Benutzer alles finden, was Sie auf einen Blick wissen müssen. Einfache farbige Symbole deuten auf den Anwesenheitsstatus anderer Benutzer hin, und Bild und Standort werden ebenfalls angezeigt.

Bei der Integration zwischen lync Server und anderen Produkten wie Outlook und SharePoint wird immer dann der Status und die Kontaktinformationen angezeigt, wenn der Name eines Kontakts angezeigt wird, beispielsweise in einer e-Mail-Nachricht oder auf einer Teamwebsite. Wenn Sie Exchange 2013 bereitstellen, können lync Server und Exchange 2013 zudem einen einheitlichen Kontaktspeicher freigeben, auf den Clients eines der beiden Produkte zugreifen können.

Mit Chatnachrichten in lync Server können Benutzer sich schnell und zeitnah über Informationen informieren. Wenn Sie möchten, können Ihre Benutzer auch mit Benutzern von öffentlichen Chat Netzwerken wie MSN/Windows Live, Yahoo\!und AOL kommunizieren. Beachten Sie, dass für öffentliche Chat Verbindungen mit Windows Live, AOL und Yahoo möglicherweise eine separate Lizenz erforderlich ist.\! Lync Server umfasst auch die Kompatibilität von Extensible Messaging and Presence Protocol (XMPP), damit Ihre Benutzer Chatnachrichten und Anwesenheitsinformationen mit Benutzern von XMPP-Diensten wie Google Talk austauschen können.

<div>


> [!IMPORTANT]  
> <UL>
> <LI>
> <P>Ab dem 1. September, 2012, ist die Microsoft lync Public im Connectivity-Benutzerabonnementlizenz ("PIC USL") nicht mehr für den Kauf von neuen oder erneuernden Vereinbarungen verfügbar. Kunden mit aktiven Lizenzen sind in der Lage, weiterhin mit Yahoo! zu verbünden Messenger, bis der Dienst das Datum beendet hat. Datum des Endes des Lebenszyklus von Juni 2014 für AOL und Yahoo! wurde angekündigt. Ausführliche Informationen finden Sie <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">unter Unterstützung für öffentliche Instant Messenger-Konnektivität in lync Server 2013</A>.</P>
> <LI>
> <P>Bei der PIC-USL handelt es sich um eine Abonnementlizenz pro Benutzer pro Monat, die für die Föderation von lync Server oder Office Communications Server mit Yahoo! erforderlich ist. Messenger. Die Möglichkeit von Microsoft, diesen Dienst bereitzustellen, war von der Unterstützung durch Yahoo! abhängig, deren zugrunde liegende Vereinbarung abgewickelt wird.</P>
> <LI>
> <P>Lync ist mehr denn je ein leistungsfähiges Tool für die Verbindung zwischen Organisationen und Personen in der ganzen Welt. Für den Verbund mit Windows Live Messenger sind keine zusätzlichen Benutzer-und Gerätelizenzen außerhalb der lync-Standard CAL erforderlich. Skype Federation wird dieser Liste hinzugefügt und ermöglicht es lync-Benutzern, Hunderte von Millionen von Personen mit Chat und Sprache zu erreichen.</P></LI></UL>



</div>

Der Konversations Verlauf ermöglicht Benutzern, alte Chat Unterhaltungen nachzuverfolgen und Informationen abzurufen, die möglicherweise bereits vor Monaten von Chatnachrichten mitgeteilt wurden.

Das Feature "beständiger Chat" ermöglicht Benutzern die Teilnahme an mehrteiligen, themenbasierten Konversationen, die im Laufe der Zeit fortbestehen. Nachrichten, die in Chatrooms (Diskussionsforen) gepostet wurden, können persistent sein (im Laufe der Zeit verfügbar), damit Personen an verschiedenen Standorten und Abteilungen teilnehmen können, selbst wenn Sie nicht alle gleichzeitig online sind.

Wenn Ihre Organisation Konformitätsrichtlinien beachten muss, können Sie eine Nachrichten Archivierungsfunktion bereitstellen, um den Inhalt von Sofortnachrichten für alle Benutzer in Ihrer Organisation oder nur für bestimmte Benutzer, die Sie angeben, zu archivieren. Wenn Sie auch Exchange 2013 bereitstellen, kann Ihr im-Archiv in das in-situ-Speicherfeature von Exchange integriert werden, um eine einheitliche Verwaltungsoberfläche für Ihre Compliance bereitzustellen.

</div>

<span> </span>

</div>

</div>

</div>

