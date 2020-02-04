---
title: 'Lync Server 2013: Migrationsüberlegungen für Besprechungen'
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
ms.openlocfilehash: 6af94514360509d4f608a21228b2fecf9a522007
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41727735"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="migration-considerations-for-meetings-in-lync-server-2013"></a>Migrationsüberlegungen für Besprechungen in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2014-02-10_

In diesem Abschnitt werden die folgenden Themen behandelt:

  - Änderungen an Besprechungen in Microsoft lync Server 2013

  - Migrieren von Benutzern basierend auf Ihren Konferenz Anforderungen

  - Migrieren vorhandener Besprechungen und Besprechungsinhalte

  - Benutzerfreundlichkeit während der Migration von lync Server 2010

  - Benutzerfreundlichkeit während der Migration von Office Communications Server 2007 R2

  - Microsoft lync 2013-Kompatibilität mit Besprechungen mit früheren Server Versionen

<div>

## <a name="changes-to-meetings-in-lync-server-2013"></a>Änderungen an Besprechungen in lync Server 2013

**Lync Server 2013-Features.**    Lync Server 2013 bietet neue Konferenzfeatures, die Benutzern zur Verfügung stehen, nachdem Ihre Konten nach lync Server 2013 verschoben wurden und sich mit dem lync 2013-Client anmelden. Neue Features werden in den [neuen Konferenzfeatures in lync Server 2013](lync-server-2013-new-conferencing-features.md) und Neuerungen [für Clients in lync Server 2013](lync-server-2013-what-s-new-for-clients.md)erläutert.

**Besprechungs-URL.**    Wie in lync Server 2010 verfügen alle neu geplanten Besprechungen in lync Server 2013 über ein URL-Präfix für https://, und vorhandene Besprechungen werden zusammen mit Benutzerkonten migriert. Lync Server 2013 unterstützt jedoch nicht den Office Communications Server 2007 R2-Konferenzanruf (conf://url prefix) oder die Webkonferenz (Meet://-URL-Präfix). Weitere Informationen finden Sie unter "Migrieren von Besprechungen von Office Communications Server 2007 R2" weiter unten in diesem Thema.

**Kundendienst.**    Im Gegensatz zu lync Server 2010 unterstützt lync Server 2013 keine Office Communicator-Clients für Konferenzen. Sie können die folgenden Clients nicht zum teilnehmen an Besprechungen verwenden, die über das Online Besprechungs-Add-in für lync 2013 geplant sind:

  - Office Communicator 2007 R2

  - Microsoft Office Communications Server 2007 R2-Vermittlung

  - Office Communicator 2007

  - Office Live Meeting 2007

Während der Migration sollten Office Communicator 2007 R2-Benutzer lync Web App 2013 verwenden, um an lync Server 2013-Besprechungen teilzunehmen, bis Ihre Clients aktualisiert wurden. Beachten Sie, dass Benutzer von Office Communicator 2007 R2 weiterhin ihren vorhandenen Client gegen lync Server 2013 für Anwesenheits-und Chat Features verwenden können, Konferenzfeatures aber nicht unterstützt werden.

<div>


</div>

</div>

<div>

## <a name="migrating-users-based-on-their-conferencing-needs"></a>Migrieren von Benutzern basierend auf Ihren Konferenz Anforderungen

**Häufige Besprechungsorganisatoren**    Ziehen Sie es vor, häufige Besprechungsorganisatoren frühzeitig zu migrieren, damit Sie die neuen lync Server 2013-und lync 2013-Features nutzen können, die in den [neuen Konferenzfeatures in lync Server 2013](lync-server-2013-new-conferencing-features.md) und Neuerungen [für Clients in lync Server 2013](lync-server-2013-what-s-new-for-clients.md)beschrieben sind.

**Live Meeting-Benutzer.**    Wenn Sie von Office Communications Server 2007 R2 migrieren, und Sie über Benutzer verfügen, die für Live Meeting spezifische Webkonferenz Features benötigen – insbesondere Unterstützung für große Besprechungen und Break-out-Räume – haben Sie die folgenden Optionen:

  - Empfehlen Sie die Organisatoren, den Live Meeting-Dienst zu verwenden, sofern Sie in Ihrer Organisation verfügbar sind.

  - Lassen Sie die Organisatoren in der früheren Version von Office Communications Server verwaltet, damit Sie weiterhin Server basierte Live Meeting-Webkonferenzen planen können.

</div>

<div>

## <a name="migrating-existing-meetings-and-meeting-content"></a>Migrieren vorhandener Besprechungen und Besprechungsinhalte

<div>

## <a name="migrating-meetings-from-lync-server-2010"></a>Migrieren von Besprechungen von lync Server 2010

Wenn Sie einen Benutzer von lync Server 2010 auf lync Server 2013 verschieben, werden die folgenden Informationen mit dem Konto des Benutzers verschoben:

  - Besprechungen, die der Benutzer bereits geplant hat. Dazu gehören Konferenzverzeichnisse und Konferenzdaten.

  - Die persönliche Identifikationsnummer (PIN) des Benutzers. Die aktuelle PIN des Benutzers funktioniert weiterhin, bis er abläuft oder der Benutzer eine neue PIN anfordert.

Die folgenden Benutzerkontoinformationen werden jedoch nicht auf den neuen Server verschoben:

  - Besprechungsinhalte, beispielsweise PowerPoint-Präsentationen, Whiteboard-Inhalte und Umfragedaten

Verwenden Sie den MoveMeetingContent-Parameter des Move-CsUser-Cmdlets, um den Inhalt zu verschieben, der in Besprechungen freigegeben wurde. Detaillierte Informationen zur Verwendung dieses Cmdlets finden Sie unter [Move-CsUser](https://docs.microsoft.com/powershell/module/skype/Move-CsUser) in der Dokumentation zu lync Server 2013-Cmdlets.

</div>

<div>

## <a name="migrating-meetings-from-office-communications-server-2007-r2"></a>Migrieren von Besprechungen von Office Communications Server 2007 R2

Office Communications Server 2007 R2-Besprechungen sind entweder Konferenzgespräche (conf://url prefix) oder Webkonferenzen (Meet://url prefix). Lync Server 2013 unterstützt diese früheren conf://-und Meet://-Konferenzen nicht, und Sie werden nicht zusammen mit dem Benutzerkonto migriert. Nach der Migration sollten Sie die Benutzer anweisen, die Links für alle geplanten Onlinebesprechungen zu aktualisieren. Sie können dies nach der Installation des lync 2013-Clients tun, indem Sie eine geplante Besprechungseinladung öffnen, die die Besprechungs-URL aktualisiert, und die Einladung an die Teilnehmer erneut senden.

</div>

</div>

<div>

## <a name="user-experience-during-lync-server-2010-migration"></a>Benutzerfreundlichkeit während der Migration von lync Server 2010

Dieser Abschnitt enthält eine Zusammenfassung der Benutzer Konferenzfunktionen bei der Migration von lync 2010. Weitere Informationen dazu, wie lync Server 2013-Clients koexistieren und mit früheren Client-und Server Versionen interagieren können, finden Sie unter [Client Interoperabilität in lync 2013](lync-server-2013-client-interoperability-in-lync-2013.md).

<div>

## <a name="joining-lync-server-2010-meetings-with-a-lync-2013-client"></a>Beitreten zu lync Server 2010-Besprechungen mit einem lync 2013-Client

Während der Migration von lync Server 2010 kann es einen Zeitraum der Koexistenz geben, wenn Benutzer mit einem lync 2013-Client an lync Server 2010-Besprechungen teilnehmen. Diese Benutzer können mit den folgenden Ausnahmen auf lync 2013-Clientfeatures zugreifen:

  - In den Verwaltungsoptionen für **Teilnehmer** , auf die durch zeigen auf das Symbol "Personen" im Besprechungsfenster zugegriffen werden kann, funktioniert die Option **keine Besprechung im Chat** .

  - Die Katalogansicht funktioniert in Videokonferenzen nicht. Der Benutzer sieht nur den aktiven Lautsprecher und nicht alle Lautsprecher. In der Liste der Optionen zum **Wählen eines Layouts** steht die **Katalogansicht** nicht zur Verfügung.

  - Die Teilnehmerliste wird standardmäßig in Videokonferenzen angezeigt.

  - Wenn Sie mit der rechten Maustaste auf einen Benutzer in der Teilnehmerliste klicken, sind die Optionen für das **Video Spotlight** und die **PIN-zu-Katalog** -Teilnehmer-Verwaltung Sperren nicht verfügbar.

</div>

</div>

<div>

## <a name="user-experience-during-office-communications-server-2007-r2-migration"></a>Benutzerfreundlichkeit während der Migration von Office Communications Server 2007 R2

Dieser Abschnitt enthält eine Zusammenfassung der Benutzer Konferenz Erfahrung bei der Migration von Office Communications Server 2007 R2, sowohl vor als auch nach der Installation von lync 2013. Weitere Informationen dazu, wie lync Server 2013-Clients koexistieren und mit früheren Client-und Server Versionen interagieren können, finden Sie unter [Client Interoperabilität in lync 2013](lync-server-2013-client-interoperability-in-lync-2013.md).

<div>

## <a name="after-user-account-is-migrated-before-lync-2013-is-installed"></a>Nach dem Migrieren des Benutzerkontos vor der Installation von lync 2013

Nachdem ein Benutzer zum lync Server 2013-Server migriert wurde, aber bevor neue Clients installiert werden, können Benutzer von Office Communicator 2007 R2 weiterhin ihren vorhandenen Client für Anwesenheits-und Chat Features mit lync Server 2013 verwenden, aber Konferenzfeatures werden nicht stützt.

</div>

<div>

## <a name="after-user-account-is-migrated-after-lync-2013-is-installed"></a>Nach dem Migrieren des Benutzerkontos nach der Installation von lync 2013

Wenn ein migrierter Benutzer lync 2013 installiert, wird auch das Online Besprechungs-Add-in für lync 2013 installiert. Dies hat die folgenden Auswirkungen:

  - Alle nachfolgend geplanten Besprechungen verwenden das neue Besprechungs Format, das eine https://-Adresse anstelle der Legacy-Meet://-Live Besprechungs Adresse verwendet.

  - Bei einer IT-verwalteten Bereitstellung von lync 2013 hat der Administrator die Möglichkeit, das Konferenz-Add-in für Microsoft Office Outlook zu deinstallieren, das zum Planen von Live Meeting-Servern und dienstbasierten Besprechungen verwendet wird. Möglicherweise verfügen Sie jedoch über Benutzer, die weiterhin Live Meeting-Service Besprechungen planen müssen. In diesem Fall können Sie zulassen, dass beide Add-ins koexistieren.

</div>

<div>

## <a name="meetings-with-federated-organizations-that-use-previous-clients"></a>Besprechungen mit Verbundorganisationen, die frühere Clients verwenden

Benutzer in Verbundorganisationen, die Microsoft Office Communicator 2007 verwenden, können in Ihrer Organisation nicht an lync Server 2013-Besprechungen teilnehmen, wenn diese Besprechungen vom Organisator gesperrt sind. Sie müssen diese Besprechungen in lync Server 2013 neu planen, sodass Sie, wenn Teilnehmer an der Besprechung teilnehmen, mithilfe der neuen https://-Besprechungs-URL, lync Web App verwenden können.

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

