---
title: 'Lync Server 2013: Zuweisen von Konferenzrichtlinien zur Unterstützung anonymer Benutzer'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Assign conferencing policies to support anonymous users
ms:assetid: 662de022-1111-40f7-bad4-f2b686f30973
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg521007(v=OCS.15)
ms:contentKeyID: 48184333
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: de154fca02470003fdedd0ff29cc8c879d1865aa
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2020
ms.locfileid: "48523192"
---
# <a name="assign-conferencing-policies-to-support-anonymous-users-in-lync-server-2013"></a>Zuweisen von Konferenzrichtlinien zur Unterstützung anonymer Benutzer in lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-10-19_

Standardmäßig werden alle Benutzer daran gehindert, anonyme Benutzer zur Teilnahme an einer Besprechung einzuladen. Sie steuern, wer anonyme Benutzer einladen kann, indem Sie eine Konferenzrichtlinie für die Unterstützung anonymer Benutzer konfigurieren und diese Konferenzrichtlinie auf bestimmte Benutzer anwenden. Ausführliche Informationen zum Konfigurieren von Konferenzrichtlinien zur Unterstützung anonymer Benutzer finden Sie unter [erstellen oder Ändern einer konferenzrichtlinie in lync Server 2013](lync-server-2013-create-or-modify-a-conferencing-policy.md) und [Verwalten des Verbunds und des externen Zugriffs auf lync Server 2013](lync-server-2013-managing-federation-and-external-access-to-lync-server-2013.md).

Verwenden Sie das Verfahren in diesem Abschnitt, um eine bereits erstellte Konferenzrichtlinie auf einen oder mehrere Benutzer oder Benutzergruppen anzuwenden.

<div>


> [!NOTE]  
> Neben der Konfiguration und Anwendung einer Richtlinie müssen Sie außerdem die Unterstützung für anonyme Benutzer für Ihre Organisation aktivieren, um Benutzern das Einladen anonymer Benutzer zu ermöglichen. Ausführliche Informationen finden Sie unter <A href="lync-server-2013-configure-policies-to-control-public-user-access.md">configure Policies to Control Public User Access in lync Server 2013</A>.



</div>

<div>

## <a name="to-configure-a-user-policy-for-anonymous-participation-in-meetings"></a>So konfigurieren Sie eine Benutzerrichtlinie für die anonyme Teilnahme an Besprechungen

1.  Melden Sie sich bei einem Benutzerkonto, das Mitglied der RTCUniversalServerAdmins-Gruppe ist (oder gleichwertige Benutzerrechte hat) oder der CsAdministrator-Rolle zugewiesen ist, an einem beliebigen Computer in ihrer internen Bereitstellung an.

2.  Öffnen Sie ein Browserfenster, und geben Sie die admin-URL ein, um das lync Server-Systemsteuerung zu öffnen. Ausführliche Informationen zu den verschiedenen Methoden, die Sie zum Starten von lync Server-Systemsteuerung verwenden können, finden Sie unter [Open lync Server 2013 Administration Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Klicken Sie in der linken Navigationsleiste auf **Konferenzen**, und führen Sie einen der folgenden Schritte aus:
    
    1.  Klicken Sie zum Erstellen einer neuen Benutzerrichtlinie auf **Neu** und anschließend auf **Benutzerrichtlinie**. Erstellen Sie einen eindeutigen Namen im Feld **Name**, der auf den Zweck der Benutzerrichtlinie hinweist (z. B. **EnableAnonymous** für eine Benutzerrichtlinie, welche die Kommunikation mit anonymen Benutzern aktiviert).
    
    2.  Klicken Sie zum Konfigurieren einer vorhandenen Benutzerrichtlinie in der Tabelle auf die entsprechende Richtlinie, klicken Sie auf **Bearbeiten** und anschließend auf **Details anzeigen**.

4.  Aktivieren Sie im Dialogfeld **Konferenzrichtlinien** das Kontrollkästchen **Teilnehmern das Einladen anonymer Benutzer gestatten**.

5.  Klicken Sie auf **Commit**.

6.  Klicken Sie in der linken Navigationsleiste auf **Benutzer**, und suchen Sie anschließend nach dem Benutzerkonto, das Sie konfigurieren möchten.

7.  Klicken Sie in der Tabelle mit den Suchergebnissen auf das Benutzerkonto, klicken Sie auf **Bearbeiten** und dann auf **Details anzeigen**.

8.  Wählen Sie in **Lync Server-Benutzer bearbeiten** unter **Konferenzrichtlinie** die Benutzerrichtlinie mit der Konfiguration für den anonymen Benutzerzugriff aus, die Sie auf diesen Benutzer anwenden möchten.
    
    <div>
    

    > [!NOTE]  
    > Durch die <STRONG> &lt; automatischen &gt; </STRONG> Einstellungen werden die Standardeinstellungen für die Server Installation übernommen und vom Server automatisch angewendet.

    
    </div>

Damit Benutzer anonyme Benutzer zu Konferenzen einladen können, müssen Sie auch die Unterstützung für anonyme Benutzer in Ihrer Organisation aktivieren. Ausführliche Informationen finden Sie unter [configure Policies to Control Public User Access in lync Server 2013](lync-server-2013-configure-policies-to-control-public-user-access.md) in der Bereitstellungsdokumentation oder in der Betriebsdokumentation.

</div>

</div>

<span> </span>

</div>

</div>

</div>

