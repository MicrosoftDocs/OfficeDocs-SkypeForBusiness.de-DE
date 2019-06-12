---
title: 'Lync Server 2013: Zuweisen von Konferenzrichtlinien zur Unterstützung anonymer Benutzer'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Assign conferencing policies to support anonymous users
ms:assetid: 662de022-1111-40f7-bad4-f2b686f30973
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg521007(v=OCS.15)
ms:contentKeyID: 48184333
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 94ff3fe520b776d6f6043abb66f9926da5acaa22
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34847894"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="assign-conferencing-policies-to-support-anonymous-users-in-lync-server-2013"></a>Zuweisen von Konferenzrichtlinien zur Unterstützung anonymer Benutzer in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-10-19_

Standardmäßig werden alle Benutzer daran gehindert, anonyme Benutzer zur Teilnahme an einer Besprechung einzuladen. Sie steuern, wer anonyme Benutzer einladen kann, indem Sie eine konferenzrichtlinie für die Unterstützung anonymer Benutzer konfigurieren und diese konferenzrichtlinie auf bestimmte Benutzer anwenden. Details zum Konfigurieren von Konferenzrichtlinien zur Unterstützung anonymer Benutzer finden Sie unter [erstellen oder Ändern einer konferenzrichtlinie in lync Server 2013](lync-server-2013-create-or-modify-a-conferencing-policy.md) und [Verwalten des Föderations-und des externen Zugriffs auf lync Server 2013](lync-server-2013-managing-federation-and-external-access-to-lync-server-2013.md).

Verwenden Sie das Verfahren in diesem Abschnitt, um eine konferenzrichtlinie anzuwenden, die Sie bereits für einen oder mehrere Benutzer oder Benutzergruppen erstellt haben.

<div>


> [!NOTE]  
> Neben der Konfiguration und Anwendung einer Richtlinie, mit der Benutzer anonyme Benutzer einladen können, müssen Sie auch die Unterstützung für anonyme Benutzer für Ihre Organisation aktivieren. Ausführliche Informationen finden Sie unter <A href="lync-server-2013-configure-policies-to-control-public-user-access.md">Konfigurieren von Richtlinien zum Steuern des Zugriffs öffentlicher Benutzer in lync Server 2013</A>.



</div>

<div>

## <a name="to-configure-a-user-policy-for-anonymous-participation-in-meetings"></a>So konfigurieren Sie eine Benutzerrichtlinie für die anonyme Teilnahme an Besprechungen

1.  Melden Sie sich mit einem Benutzerkonto, das Mitglied der Gruppe "RTCUniversalServerAdmins" ist (oder über gleichwertige Benutzerrechte verfügt) oder dem die Rolle "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.

2.  Öffnen Sie ein Browserfenster, und geben Sie dann die Administrator-URL ein, um die lync Server-Systemsteuerung zu öffnen. Details zu den verschiedenen Methoden, die Sie zum Starten der lync Server-Systemsteuerung verwenden können, finden Sie unter [Öffnen von lync Server 2013-Verwaltungstools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Klicken Sie in der linken Navigationsleiste auf **Konferenzen**, und führen Sie dann eine der folgenden Aktionen aus:
    
    1.  Klicken Sie zum Erstellen einer neuen Benutzerrichtlinie auf **neu**, und klicken Sie dann auf **Benutzerrichtlinie**. Erstellen Sie im Feld **Name** einen eindeutigen Namen, der angibt, was die Benutzerrichtlinie umfasst (beispielsweise **EnableAnonymous** für eine Benutzerrichtlinie, die die Kommunikation mit anonymen Benutzern ermöglicht).
    
    2.  Wenn Sie eine vorhandene Benutzerrichtlinie konfigurieren möchten, klicken Sie auf die entsprechende Richtlinie, die in der Tabelle aufgeführt ist, klicken Sie auf **Bearbeiten**, und klicken Sie dann auf **Details anzeigen**.

4.  Aktivieren Sie im Dialogfeld **Konferenzrichtlinien** das Kontrollkästchen Teilnehmern die Möglichkeit geben, **anonyme Benutzer einzuladen** .

5.  Klicken Sie auf **Commit ausführen**.

6.  Klicken Sie in der linken Navigationsleiste auf **Benutzer**, suchen Sie nach dem Benutzerkonto, das Sie konfigurieren möchten.

7.  Klicken Sie in der Tabelle mit den Suchergebnissen auf das Benutzerkonto, klicken Sie auf **Bearbeiten** und dann auf **Details anzeigen**.

8.  Wählen Sie in **lync Server-Benutzer bearbeiten** unter **konferenzrichtlinie**die Benutzerrichtlinie mit der Konfiguration für den anonymen Benutzer Zugriff aus, die Sie auf diesen Benutzer anwenden möchten.
    
    <div>
    

    > [!NOTE]  
    > Die <STRONG> &lt;automatischen&gt; </STRONG> Einstellungen wenden die Standardeinstellungen für Server Installationen an und werden automatisch vom Server angewendet.

    
    </div>

Damit Benutzer anonyme Benutzer zu Konferenzen einladen können, müssen Sie auch die Unterstützung für anonyme Benutzer in Ihrer Organisation aktivieren. Ausführliche Informationen finden Sie unter [Konfigurieren von Richtlinien zum Steuern des Zugriffs öffentlicher Benutzer in lync Server 2013](lync-server-2013-configure-policies-to-control-public-user-access.md) in der Bereitstellungsdokumentation oder in der Betriebsdokumentation.

</div>

</div>

<span> </span>

</div>

</div>

</div>

