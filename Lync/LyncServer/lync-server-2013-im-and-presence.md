---
title: 'Lync Server 2013: Chat und Anwesenheit'
TOCTitle: Chat und Anwesenheit
ms:assetid: 6a93ae95-3b64-410b-ab72-74dea232f065
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg417162(v=OCS.15)
ms:contentKeyID: 49294302
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Chat und Anwesenheit in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2013-10-07_

Die Funktionalität für Chatnachrichten und Anwesenheit ist in jeder Lync Server-Bereitstellung automatisch installiert.

*Anwesenheitsinformationen* ermöglichen es Benutzern, Kollegen zum richtigen Zeitpunkt und über den richtigen Kommunikationskanal zu erreichen und erhöhen so die Produktivität in der Arbeitsumgebung. Zu den Anwesenheitsinformationen eines Benutzers gehören Informationen wie Verfügbarkeit, Kommunikationsbereitschaft, weitere Hinweise (z. B. Standort und Status) und Angaben dazu, über welchen Kommunikationskanal der Benutzer erreichbar ist. Die Anwesenheitsinformationen wurden in Lync Server durch den Einsatz von Bildern, Standortinformationen und eine umfangreiche Auswahl an Anwesenheitszuständen erweitert, wie zum Beispiel "Nicht bei der Arbeit", "Nicht stören" und "Bin gleich zurück" (zusätzlich zu grundlegenden Statusinformationen wie "Verfügbar", "Beschäftigt" und "In einer Konferenz"). Administratoren können außerdem benutzerdefinierte, organisationsspezifische Anwesenheitszustände definieren.

Mit der Kontaktverwaltung und den Benutzerzugriffsoptionen können Benutzer steuern, welche Informationen anderen Benutzern angezeigt werden. Benutzer können verschiedene Kontaktebenen festlegen, für die jeweils verschiedene Stufen von Anwesenheitsinformationen angezeigt werden.

Mit einem einfachen Blick auf eine Kontaktliste erhalten Benutzer alle für sie relevanten Informationen. Einfache farbige Symbole weisen auf den Anwesenheitsstatus anderer Benutzer hin, und es werden Bilder und Standorte angezeigt.

Dank der Integration von Lync Server mit anderen Produkten (wie Outlook und SharePoint) werden überall dort, wo der Name eines Kontakts angezeigt wird (wie zum Beispiel in einer E-Mail-Nachricht oder auf einer Teamwebsite), auch Status- und Kontaktinformationen eingeblendet. Außerdem können (wenn Exchange 2013 bereitgestellt ist) Lync Server und Exchange 2013 einen einheitlichen Kontaktspeicher nutzen, auf den über Clients eines der beiden Produkte zugegriffen werden kann.

Mit der Chatnachrichtenfunktion in Lync Server können Benutzer schnell und unkompliziert miteinander kommunizieren. Falls gewünscht, können Sie Ihren Benutzern auch die Kommunikation mit Benutzern anderer öffentlicher Instant Messaging-Systeme (wie MSN/Windows Live, Yahoo\! und AOL) erlauben. Beachten Sie dabei, dass für öffentliche Chatnachrichtenverbindungen mit Windows Live, AOL und Yahoo\! möglicherweise eine separate Lizenz erforderlich ist. Lync Server verfügt auch über XMPP-Kompatibilität (Extensible Messaging and Presence Protocol), sodass Ihre Benutzer auch Chatnachrichten und Anwesenheitsinformationen mit Benutzern von XMPP-Diensten (wie Google Talk) austauschen können.


> [!IMPORTANT]
> <UL>
> <LI>
> <P>Ab dem 1. September 2012 kann die Microsoft Lync-Benutzerabonnementlizenz für die Verbindung mit öffentlichen Chatdiensten ("PIC USL") nicht mehr neu erworben werden, und Verträge können nicht verlängert werden. Kunden mit aktiven Lizenzen können den Partnerverbund mit Yahoo! Messenger weiterhin nutzen, bis der Dienst eingestellt wird. Als Datum der Einstellung des Diensts für AOL und Yahoo! wurde Juni 2014 angekündigt. Einzelheiten hierzu finden Sie unter <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Unterstützen von Verbindungen mit öffentlichen Chatdiensten in Lync Server 2013</A>.</P>
> <LI>
> <P>Bei PIC&nbsp;USL handelt es sich um eine Abonnementlizenz pro Benutzer und pro Monat, die für Lync&nbsp;Server oder Office&nbsp;Communications&nbsp;Server zum Einrichten eines Partnerverbunds mit Yahoo! Messenger erforderlich ist. Die Bereitstellung dieses Services durch Microsoft hing von der Unterstützung durch Yahoo! ab, deren zugrundeliegende Vereinbarung ausläuft.</P>
> <LI>
> <P>Lync ist mehr denn je ein leistungsstarkes Tool das Organisationen und Einzelpersonen weltweit verbindet. Der Partnerverbund mit Windows Live Messenger erfordert keine zusätzlichen Benutzer-/Gerätelizenzen außer der Lync Standard CAL. Der Partnerverbund mit Skype wird dieser Liste hinzugefügt und ermöglicht Lync-Benutzern, Abermillionen von Personen per Chat oder VoIP zu erreichen.</P></LI></UL>



Anhand der aufgezeichneten Unterhaltungen können Benutzer ihre älteren Chatnachrichten verfolgen und Informationen abrufen, die möglicherweise Monate zuvor per Chatnachricht mitgeteilt wurden.

Die Funktion Beständiger Chat versetzt Benutzer in die Lage, an themenbasierten Unterhaltungen mit mehreren Teilnehmern teilzunehmen, die sich über längere Zeiträume erstrecken. In Chatrooms (Diskussionsforen) veröffentlichte Nachrichten können langlebig sein (d. h. dauerhaft verfügbar), sodass Benutzer aus unterschiedlichen Standorten und Abteilungen an dem Chat teilnehmen können, selbst wenn sie nicht alle zum gleichen Zeitpunkt online sind.

Wenn Ihre Organisation rechtliche Vorschriften bezüglich Compliance einhalten muss, können Sie eine Archivierungsfunktion für Nachrichten bereitstellen, um die Inhalte von Chatnachrichten für alle Benutzer in Ihrer Organisation oder auch nur für bestimmte festgelegte Benutzer zu archivieren. Wenn Sie auch Exchange 2013 bereitstellen, kann Ihr Chatnachrichtenarchiv mit der Compliance-Archiv-Funktion von Exchange integriert werden, was eine zentrale Verwaltbarkeit für Ihre Compliance-Vorkehrungen ermöglicht.

