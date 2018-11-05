---
title: Migrationsüberlegungen für Besprechungen
TOCTitle: Migrationsüberlegungen für Besprechungen
ms:assetid: a9807d58-99a3-4cff-b4c6-74950d106a2b
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg412800(v=OCS.15)
ms:contentKeyID: 61140484
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Migrationsüberlegungen für Besprechungen

 

_**Letztes Änderungsdatum des Themas:** 2014-02-10_

In diesem Abschnitt werden die folgenden Themen dargestellt:

  - Änderungen an Besprechungen in Microsoft Lync Server 2013

  - Migrieren von Benutzern auf der Basis ihrer Konferenzanforderungen

  - Migrieren vorhandener Besprechungen und Besprechungsinhalte

  - Benutzerfreundlichkeit während der Lync Server 2010-Migration

  - Benutzerfreundlichkeit während der Office Communications Server 2007 R2-Migration

  - Microsoft Lync 2013-Kompatibilität mit Besprechungen in früheren Serverversionen

## Änderungen an Besprechungen in Lync Server 2013

**Lync Server 2013-Funktionen.**   Lync Server 2013 bietet neue Konferenzfunktionen, die Benutzern zur Verfügung stehen, nachdem ihre Konten zu Lync Server 2013 verschoben wurden und sie sich beim Lync 2013-Client angemeldet haben. Die neuen Funktionen sind unter [Neue Konferenzfunktionen in Lync Server 2013](lync-server-2013-new-conferencing-features.md) und [Neue Funktionen für Clients in Lync Server 2013](lync-server-2013-what-s-new-for-clients.md) näher dargestellt.

**Besprechungs-URL.**   Wie in Lync Server 2010 haben alle neu geplanten Besprechungen in Lync Server 2013 das URL-Präfix "https://" und vorhandene Besprechungen werden gemeinsam mit Benutzerkonten migriert. Allerdings bietet Lync Server 2013 keine Unterstützung für den Office Communications Server 2007 R2-Konferenzanruf (URL-Präfix "conf://") oder die Webkonferenz (URL-Präfix "meet://"). Weitere Informationen finden Sie unter “Migrieren von Besprechungen von Office Communications Server 2007 R2” später in diesem Thema.

**Clientunterstützung.**   Im Gegensatz zu Lync Server 2010 bietet Lync Server 2013 keine Unterstützung für Office Communicator-Clients in Konferenzen. Sie können die folgenden Clients nicht verwenden, um an Besprechungen teilzunehmen, die über das Onlinebesprechungs-Add-In für Lync 2013 geplant wurden:

  - Office Communicator 2007 R2

  - Microsoft Office Communications Server 2007 R2-Vermittlung

  - Office Communicator 2007

  - Office Live Meeting 2007

Während der Migration sollten Office Communicator 2007 R2-Benutzer Lync Web App 2013 verwenden, um an Lync Server 2013-Besprechungen teilzunehmen, bis ihre Clients aktualisiert wurden. Beachten Sie, dass Office Communicator 2007 R2-Benutzer weiterhin ihre vorhandenen Clients für Anwesenheits- und Chatfunktionen mit Lync Server 2013 verwenden können, aber Konferenzfunktionen nicht unterstützt werden.


## Migrieren von Benutzern auf der Basis ihrer Konferenzanforderungen

**Organisatoren häufiger Besprechungen.**   Ziehen Sie die Migration von Organisatoren häufiger Besprechungen zu einem frühen Zeitpunkt im Prozess in Betracht, damit sie die neuen Lync Server 2013- und Lync 2013-Funktionen verwenden können, die unter [Neue Konferenzfunktionen in Lync Server 2013](lync-server-2013-new-conferencing-features.md) und [Neue Funktionen für Clients in Lync Server 2013](lync-server-2013-what-s-new-for-clients.md) aufgeführt sind.

**Live Meeting-Benutzer.**   Wenn Sie von Office Communications Server 2007 R2 migrieren und Benutzer haben, die für Live Meeting spezifische Webkonferenzfunktionen benötigen – insbesondere Unterstützung für große Besprechungen und Break-out-Räume –, haben Sie die folgenden Optionen:

  - Raten Sie Organisatoren, den Live Meeting-Dienst zu verwenden, wenn dieser in Ihrem Unternehmen verfügbar ist.

  - Verwalten Sie die Organisatoren weiterhin in der früheren Version von Office Communications Server, damit sie weiter serverbasierte Live Meeting-Webkonferenzen planen können.

## Migrieren vorhandener Besprechungen und Besprechungsinhalte

## Migrieren von Besprechungen von Lync Server 2010

Wenn Sie einen Benutzer von Lync Server 2010 zu Lync Server 2013 verschieben, werden die folgenden Informationen mit dem Benutzerkonto verschoben:

  - Vom Benutzer bereits geplante Besprechungen. Dies beinhaltet Konferenzverzeichnisse und Konferenzdaten.

  - Die persönliche Identifikationsnummer (PIN) des Benutzers: Die aktuelle PIN des Benutzers ist weiterhin solange gültig, bis sie abläuft oder der Benutzer eine neue PIN anfordert.

Die folgenden Benutzerkontoinformationen werden jedoch nicht auf den neuen Server verschoben:

  - Besprechungsinhalte, zum Beispiel PowerPoint-Präsentationen, Whiteboardinhalte und Umfragedaten

Verwenden Sie zum Verschieben der Inhalte, die in Besprechungen freigegeben wurden, den Paramter "MoveMeetingContent" des Cmdlets "Move-CsUser". Ausführliche Informationen zur Verwendung dieses Cmdlets finden Sie unter [Move-CsUser](https://docs.microsoft.com/en-us/powershell/module/skype/Move-CsUser) in der Lync Server 2013-Cmdlet-Dokumentation.

## Migrieren von Besprechungen von Office Communications Server 2007 R2

Office Communications Server 2007 R2-Besprechungen sind entweder Konferenzanrufe (URL-Präfix "conf://") oder Webkonferenzen (URL-Präfix "meet://"). Lync Server 2013 bietet keine Unterstützung für diese früheren "conf://"- und "meet://"-Konferenzen und sie werden nicht zusammen mit dem Benutzerkonto migriert. Nach der Migration sollten Sie Benutzer anweisen, die Links für alle Onlinebesprechungen zu aktualisieren, die sie geplant haben. Dies können sie nach der Installation des Lync 2013-Clients tun, indem sie die Einladung einer geplanten Besprechung öffnen, wodurch die Besprechungs-URL aktualisiert wird, und die Einladung erneut an die Teilnehmer senden.

## Benutzerfreundlichkeit während der Lync Server 2010-Migration

In diesem Abschnitt wird eine Zusammenfassung der Konferenzbenutzerfreundlichkeit bei der Migration von Lync 2010 bereitgestellt. Ausführlichere Informationen zur Koexistenz und Interaktion von Lync Server 2013-Clients mit früheren Client- und Serverversionen finden Sie unter [Clientinteroperabilität in Lync 2013](lync-server-2013-client-interoperability-in-lync-2013.md).

## Teilnehmen an Lync Server 2010-Besprechungen mit einem Lync 2013-Client

Während der Migration von Lync Server 2010 gibt es möglicherweise einen Zeitraum der Koexistenz, wenn Benutzer mit einem Lync 2013-Client an Lync Server 2010-Besprechungen teilnehmen. Diese Benutzer haben Zugriff auf Lync 2013-Clientfunktionen mit den folgenden Ausnahmen:

  - Bei den Verwaltungsoptionen für **Teilnehmer**, auf die zugegriffen werden kann, indem Sie im Besprechungsfenster auf das Symbol für Personen zeigen, funktioniert die Option **Kein Besprechungs-Chat** nicht.

  - In Videokonferenzen funktioniert die Katalogansicht nicht. Der Benutzer sieht nur den aktiven und nicht alle Sprecher. In der Liste mit Optionen für **Ein Layout auswählen** ist **Katalogansicht** nicht verfügbar.

  - Die Teilnehmerliste wird in Videokonferenzen standardmäßig angezeigt.

  - Wenn Sie mit der rechten Maustaste auf einen Benutzer in der Teilnehmerliste klicken, sind die Teilnehmerverwaltungsoptionen **Videospotlight sperren** und **An Katalog anheften** nicht verfügbar.

## Benutzerfreundlichkeit während der Office Communications Server 2007 R2-Migration

In diesem Abschnitt wird eine Zusammenfassung der Konferenzbenutzerfreundlichkeit bei der Migration von Office Communications Server 2007 R2 vor und nach der Installation von Lync 2013 bereitgestellt. Ausführlichere Informationen zur Koexistenz und Interaktion von Lync Server 2013-Clients mit früheren Client- und Serverversionen finden Sie unter [Clientinteroperabilität in Lync 2013](lync-server-2013-client-interoperability-in-lync-2013.md).

## Nach der Migration des Benutzerkontos, vor der Installation von Lync 2013

Nachdem ein Benutzer zum Lync Server 2013-Server migriert wurde, aber bevor neue Clients installiert wurden, können Office Communicator 2007 R2-Benutzer weiterhin ihren vorhandenen Client für Anwesenheits- und Chatfunktionen mit Lync Server 2013 verwenden, aber Konferenzfunktionen werden nicht unterstützt.

## Nach der Migration des Benutzerkontos, nach der Installation von Lync 2013

Wenn ein migrierter Benutzer Lync 2013 installiert, wird auch das Onlinebesprechungs-Add-in für Lync 2013 installiert. Das hat die folgenden Auswirkungen:

  - Alle nachfolgend geplanten Besprechungen verwenden das neue Besprechungsformat, in dem eine "https://"-Adresse anstelle der älteren Live Meeting Adresse "meet://" verwendet wird.

  - In einer von der IT verwalteten Bereitstellung von Lync 2013 hat der Administrator die Option, das Konferenz-Add-in für Microsoft Office Outlook zu deinstallieren, das für die Planung von Live Meeting-Server- und dienstbasierten Besprechungen verwendet wird. Möglicherweise haben Sie jedoch Benutzer, die weiterhin Live Meeting-Dienstbesprechungen planen müssen. In diesem Fall können Sie zulassen, dass beide Add-ins koexistieren.

## Besprechungen mit Partnerorganisationen, die frühere Clients verwenden

Benutzer in Partnerorganisationen, die Microsoft Office Communicator 2007 verwenden, können nicht an Lync Server 2013-Besprechungen in Ihrer Organisation teilnehmen, wenn diese Besprechungen vom Organisator gesperrt wurden. Sie müssen diese Besprechungen in Lync Server 2013 erneut planen, damit Partnerteilnehmer, die über die neue "https://"-Besprechungs-URL an der Besprechung teilnehmen, Lync Web App verwenden können.

