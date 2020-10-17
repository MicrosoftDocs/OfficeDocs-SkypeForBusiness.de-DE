---
title: 'Lync Server 2013: Überlegungen zur Migration für Besprechungen'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Migration considerations for meetings
ms:assetid: a9807d58-99a3-4cff-b4c6-74950d106a2b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412800(v=OCS.15)
ms:contentKeyID: 61097556
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 48ee24dca1cdf083de990ef42dae4017ed927e15
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2020
ms.locfileid: "48524562"
---
# <a name="migration-considerations-for-meetings-in-lync-server-2013"></a>Migrationsüberlegungen für Besprechungen in lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2014-02-10_

In diesem Abschnitt werden die folgenden Themen erläutert:

  - Änderungen an Besprechungen in Microsoft lync Server 2013

  - Migrieren von Benutzern basierend auf ihren Konferenzanforderungen

  - Migrieren von vorhandenen Besprechungen und Besprechungsinhalten

  - Benutzererfahrung während lync Server 2010 Migration

  - Benutzererfahrung während Office Communications Server 2007 R2 Migration

  - Microsoft lync 2013 Kompatibilität mit Besprechungen in früheren Server Versionen

<div>

## <a name="changes-to-meetings-in-lync-server-2013"></a>Änderungen an Besprechungen in lync Server 2013

**Lync Server 2013 Funktionen.**     Lync Server 2013 stellt neue Konferenzfeatures bereit, die Benutzern zur Verfügung stehen, nachdem Ihre Konten in lync Server 2013 verschoben wurden und sich mit dem lync 2013-Client anmelden. Neue Features werden in [neuen Konferenzfeatures in lync Server 2013](lync-server-2013-new-conferencing-features.md) und Neuerungen [für Clients in lync Server 2013](lync-server-2013-what-s-new-for-clients.md)erläutert.

**Besprechungs-URL.**     Wie in lync Server 2010 verfügen alle neu geplanten Besprechungen in lync Server 2013 über ein URL-Präfix für https://, und vorhandene Besprechungen werden zusammen mit Benutzerkonten migriert. Lync Server 2013 unterstützt jedoch nicht die Office Communications Server 2007 R2-Telefonkonferenz (conf://-URL-Präfix) oder Webkonferenz (Meet://-URL-Präfix). Weitere Informationen finden Sie unter "Migrieren von Besprechungen aus Office Communications Server 2007 R2" weiter unten in diesem Thema.

**Client Unterstützung.**     Im Gegensatz zu lync Server 2010 unterstützt lync Server 2013 keine Office Communicator-Clients für Konferenzen. Sie können die folgenden Clients nicht verwenden, um an Besprechungen teilzunehmen, die über das Online-Besprechungs-Add-in für lync 2013 geplant wurden:

  - Office Communicator 2007 R2

  - Microsoft Office Communications Server 2007 R2 Attendant

  - Office Communicator 2007

  - Office Live Meeting 2007

Während der Migration sollten Office Communicator 2007 R2 Benutzer lync Web App 2013 verwenden, um lync Server 2013 Besprechungen teilzunehmen, bis Ihre Clients aktualisiert wurden. Beachten Sie, dass Office Communicator 2007 R2 Benutzer weiterhin ihren vorhandenen Client für die lync Server 2013 für Anwesenheits-und Chatfunktionen verwenden können, aber Konferenzfeatures werden nicht unterstützt.

<div>


</div>

</div>

<div>

## <a name="migrating-users-based-on-their-conferencing-needs"></a>Migrieren von Benutzern basierend auf ihren Konferenzanforderungen

**Häufige Besprechungsorganisatoren.**     Ziehen Sie es vor, häufige Besprechungsorganisatoren frühzeitig zu migrieren, damit Sie die neuen lync Server 2013 und lync 2013 Features nutzen können, die in [neuen Konferenzfeatures in lync Server 2013](lync-server-2013-new-conferencing-features.md) und Neuerungen [für Clients in lync Server 2013](lync-server-2013-what-s-new-for-clients.md)erläutert werden.

**Live Meeting Benutzer.**     Wenn Sie von Office Communications Server 2007 R2 migrieren und über Benutzer verfügen, die spezielle Webkonferenz Features für Live Meeting benötigen – insbesondere Unterstützung für große Besprechungen und Break-out-Räume – haben Sie die folgenden Optionen:

  - Empfehlen Sie Organisatoren die Verwendung des Live Meeting-Diensts (falls in Ihrer Organisation vorhanden).

  - Lassen Sie die Organisatoren in der früheren Version von Office Communications Server verwaltet, damit Sie weiterhin Server basierte Live Meeting-Webkonferenzen planen können.

</div>

<div>

## <a name="migrating-existing-meetings-and-meeting-content"></a>Migrieren von vorhandenen Besprechungen und Besprechungsinhalten

<div>

## <a name="migrating-meetings-from-lync-server-2010"></a>Migrieren von Besprechungen aus lync Server 2010

Wenn Sie einen Benutzer aus lync Server 2010 in lync Server 2013 verschieben, werden die folgenden Informationen mit dem Konto des Benutzers verschoben:

  - Vom Benutzer bereits geplante Besprechungen. Dies umfasst Konferenzverzeichnisse und Konferenzdaten.

  - Die persönliche Identifikationsnummer (PIN) des Benutzers. Die aktuelle PIN des Benutzers ist weiterhin solange gültig, bis sie abläuft oder der Benutzer eine neue PIN anfordert.

Die folgenden Benutzerkontoinformationen werden jedoch nicht auf den neuen Server umsteigen:

  - Besprechungsinhalte, beispielsweise PowerPoint-Präsentationen, Whiteboard-Inhalte und Umfragedaten

Verwenden Sie den MoveMeetingContent-Parameter des Move-CsUser-Cmdlets, um den Inhalt zu verlagern, der in Besprechungen freigegeben wurde. Ausführliche Informationen zur Verwendung dieses Cmdlets finden Sie unter CsUser in der Dokumentation zu lync Server 2013 [-](https://docs.microsoft.com/powershell/module/skype/Move-CsUser) Cmdlets.

</div>

<div>

## <a name="migrating-meetings-from-office-communications-server-2007-r2"></a>Migrieren von Besprechungen aus Office Communications Server 2007 R2

Office Communications Server 2007 R2 Besprechungen sind entweder Konferenzanrufe (conf://-URL-Präfix) oder Webkonferenzen (Meet://-URL-Präfix). Diese früheren conf://-und Meet://-Konferenzen werden von lync Server 2013 nicht unterstützt, und Sie werden nicht zusammen mit dem Benutzerkonto migriert. Nach der Migration sollten Sie die Benutzer anweisen, die Links für alle geplanten Onlinebesprechungen zu aktualisieren. Dies können Sie nach der Installation des lync 2013 Clients durchführen, indem Sie eine geplante Besprechungseinladung öffnen, die die Besprechungs-URL aktualisiert und die Einladung erneut an die Teilnehmer sendet.

</div>

</div>

<div>

## <a name="user-experience-during-lync-server-2010-migration"></a>Benutzererfahrung während lync Server 2010 Migration

Dieser Abschnitt enthält eine Zusammenfassung der Benutzer Konferenz Erfahrung bei der Migration von lync 2010. Weitere Informationen zur Koexistenz von lync Server 2013-Clients und zur Interaktion mit vorherigen Client-und Server Versionen finden Sie unter [Client Interoperabilität in lync 2013](lync-server-2013-client-interoperability-in-lync-2013.md).

<div>

## <a name="joining-lync-server-2010-meetings-with-a-lync-2013-client"></a>Beitreten lync Server 2010 Besprechungen mit einem lync 2013-Client

Während der Migration von lync Server 2010 kann es eine gewisse Koexistenz geben, wenn Benutzer lync Server 2010 Besprechungen mit einem lync 2013-Client beitreten. Diese Benutzer haben Zugriff auf lync 2013 Clientfeatures mit den folgenden Ausnahmen:

  - In den Verwaltungsoptionen für **Teilnehmer** , auf die durch den Hinweis auf das Symbol Personen im Besprechungsfenster zugegriffen werden kann, funktioniert die Option **keine Besprechungs-Chat** Funktion nicht.

  - Die Katalogansicht funktioniert nicht in Videokonferenzen. Der Benutzer sieht anstelle aller Lautsprecher nur den aktiven Lautsprecher. In der Liste der Optionen zum **Auswählen eines Layouts** ist die **Katalogansicht** nicht verfügbar.

  - Die Teilnehmerliste wird standardmäßig in Videokonferenzen angezeigt.

  - Wenn Sie mit der rechten Maustaste auf einen Benutzer in der Teilnehmerliste klicken, sind die Verwaltungsoptionen **Video Spotlight** und **PIN-an-Katalog** -Teilnehmerverwaltung Sperren nicht verfügbar.

</div>

</div>

<div>

## <a name="user-experience-during-office-communications-server-2007-r2-migration"></a>Benutzererfahrung während Office Communications Server 2007 R2 Migration

Dieser Abschnitt enthält eine Zusammenfassung der Benutzer Konferenz Erfahrung bei der Migration von Office Communications Server 2007 R2, sowohl vor als auch nach der Installation von lync 2013. Weitere Informationen zur Koexistenz von lync Server 2013-Clients und zur Interaktion mit vorherigen Client-und Server Versionen finden Sie unter [Client Interoperabilität in lync 2013](lync-server-2013-client-interoperability-in-lync-2013.md).

<div>

## <a name="after-user-account-is-migrated-before-lync-2013-is-installed"></a>Nachdem das Benutzerkonto migriert wurde, bevor lync 2013 installiert ist

Nachdem ein Benutzer zum lync Server 2013 Server migriert wurde, aber bevor neue Clients installiert werden, können Office Communicator 2007 R2 Benutzer den vorhandenen Client weiterhin für die lync Server 2013 von Anwesenheits-und Chat Features verwenden, aber Konferenzfeatures werden nicht unterstützt.

</div>

<div>

## <a name="after-user-account-is-migrated-after-lync-2013-is-installed"></a>Nachdem das Benutzerkonto migriert wurde, nachdem lync 2013 installiert wurde

Wenn ein migrierter Benutzer lync 2013 installiert, wird auch das Online Besprechungs-Add-in für lync 2013 installiert. Dies hat folgende Auswirkungen:

  - Alle nachfolgend geplanten Besprechungen verwenden das neue Besprechungsformat mit einer Adresse vom Typ "https://" anstatt der früheren Live Meeting-Adresse vom Typ "meet://".

  - In einer IT-verwalteten Bereitstellung von lync 2013 hat der Administrator die Möglichkeit, die Add-in für Konferenzen für Microsoft Office Outlook zu deinstallieren, die zum Planen von Live Meeting Server-und dienstbasierten Besprechungen verwendet wird. Möglicherweise müssen einige Benutzer jedoch weiterhin auf Live Meeting-Diensten basierte Besprechungen planen. In einem solchen Fall ist es möglich, die gemeinsame Ausführung beider Add-Ins zuzulassen.

</div>

<div>

## <a name="meetings-with-federated-organizations-that-use-previous-clients"></a>Besprechungen mit Verbundorganisationen, die frühere Clients verwenden

Benutzer in Verbundorganisationen, die Microsoft Office Communicator 2007 verwenden, können in Ihrer Organisation nicht an lync Server 2013 Besprechungen teilnehmen, wenn diese Besprechungen vom Organisator gesperrt sind. Sie müssen diese Besprechungen in lync Server 2013 neu planen, sodass Sie lync Web App verwenden können, wenn Partner Teilnehmer der Besprechung mithilfe der neuen https://-Besprechungs-URL beitreten.

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

