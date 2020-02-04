---
title: 'Lync Server 2013: Öffnen der lync Server-Verwaltungstools'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Open Lync Server administrative tools
ms:assetid: 8c58de94-9e0a-4368-9e14-9afcaa1142d0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg195741(v=OCS.15)
ms:contentKeyID: 48184778
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3f3c1b2eec210b22bc45a27c9635507c7ad83553
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41755829"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="open-lync-server-2013-administrative-tools"></a>Öffnen der lync Server 2013-Verwaltungstools

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-06-28_

Sie können die in diesem Thema beschriebenen Verfahren verwenden, um administrative Tools zum Bereitstellen, konfigurieren oder behandeln von Problemen mit der lync Server 2013-Topologie zu öffnen.

  - Bereitstellungs-Assistent

  - Topologie-Generator

  - Lync Server-Systemsteuerung

  - Lync Server-Verwaltungsshell

<span id="BKMK_OpenDeploymentWizard"></span>

<div>

## <a name="deployment-wizard"></a>Bereitstellungs-Assistent

Gehen Sie wie folgt vor, um den Bereitstellungs-Assistenten lokal zu starten, um lync Server 2013-Komponentendateien hinzuzufügen oder zu entfernen.

<div>

## <a name="to-start-lync-server-2013-deployment-wizard"></a>So starten Sie den lync Server 2013-Bereitstellungs-Assistenten

1.  Melden Sie sich bei dem Computer an, auf dem der lync Server-Bereitstellungs-Assistent als Mitglied der Gruppe "Domänen-Admins" und der Gruppe "RTCUniversalServerAdmins" installiert ist.

2.  Klicken Sie auf **Start**, klicken Sie auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server-Bereitstellungs-Assistent**.

</div>

</div>

<span id="BKMK_OpenTopologyBuilder"></span>

<div>

## <a name="topology-builder"></a>Topologie-Generator

Gehen Sie wie folgt vor, um den Topologie-Generator zu öffnen, um die Server zu definieren, die in ihrer lync Server 2013-Topologie bereitgestellt werden sollen.

<div>

## <a name="to-open-lync-server-2013-topology-builder-to-design-the-topology"></a>So öffnen Sie den lync Server 2013-Topologie-Generator zum Entwerfen der Topologie

1.  Melden Sie sich auf dem Computer, auf dem der Topologie-Generator installiert ist, als Mitglied der Gruppe "Domänen-Admins" oder "RTCUniversalServerAdmins" an.
    
    <div>
    

    > [!NOTE]  
    > Sie können eine Topologie mithilfe eines Kontos definieren, das ein Mitglied der lokalen Benutzergruppe ist, aber zum Lesen, veröffentlichen oder Aktivieren einer Topologie, die für die Installation von lync Server 2013 auf einem Server erforderlich ist, müssen Sie ein Konto verwenden, das ein Mitglied der Gruppe der Domänenadministratoren und der RTCUniv ist. ersalServerAdmins-Gruppe, die über Vollzugriffsberechtigungen (also lesen, schreiben und ändern) für die Dateifreigabe verfügt, die Sie für den Archivierungsdatei Speicher verwenden werden, damit der Topologie-Generator die erforderlichen DACLs (Discretionary Access Control List) konfigurieren kann. oder ein Konto mit entsprechenden Benutzerrechten.

    
    </div>

2.  Starten Sie den Topologie-Generator: Klicken Sie auf **Start**, klicken Sie auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server Topology Builder**.

</div>

</div>

<span id="BKMK_OpenControlPanel"></span>

<div>

## <a name="lync-server-2013-control-panel"></a>Systemsteuerung für Lync Server 2013

Führen Sie eines der folgenden Verfahren aus, um die lync Server 2013-Systemsteuerung zu öffnen, um die Konfiguration von Servern, Benutzern, Clients und Geräten in Ihrer Umgebung zu verwalten.

<div>


> [!NOTE]  
> Sie können ein Benutzerkonto verwenden, das der CsAdministrator-Rolle zugewiesen ist, um eine beliebige Aufgabe in der lync Server 2013-Systemsteuerung auszuführen. Sie können andere Rollen verwenden, um sich bei der lync Server 2013-Systemsteuerung anzumelden, um bestimmte Verwaltungsaufgaben auszuführen, abhängig von der Aufgabe, die Sie ausführen müssen. So können Sie beispielsweise CSArchivingAdministrator verwenden, um die Archivierung in der lync Server 2013-Systemsteuerung zu verwalten. Details zu Rollen finden Sie unter <A href="lync-server-2013-planning-for-role-based-access-control.md">Planen der rollenbasierten Zugriffssteuerung in lync Server 2013</A> in der Planungsdokumentation. Details zu den Rollen, die Sie zum Ausführen einer bestimmten Aufgabe verwenden können, finden Sie in der Dokumentation der Aufgabe.



</div>

<div>

## <a name="to-open-lync-server-2013-control-panel-from-any-computer-inside-your-organizations-firewall"></a>So öffnen Sie die lync Server 2013-Systemsteuerung von einem beliebigen Computer in der Firewall Ihrer Organisation

1.  Melden Sie sich bei einem Benutzerkonto, das der Rolle CsAdministrator oder einer anderen Rolle zugewiesen ist, die über die entsprechenden Benutzerrechte und Berechtigungen für die auszuführende Aufgabe verfügt, bei einem beliebigen Computer in ihrer internen Bereitstellung mit einer Mindestauflösung von 1024 x 768 an.
    
    <div>
    

    > [!IMPORTANT]  
    > Wenn Sie eine einfache URL (Uniform Resource Locator) für die Verwaltung konfiguriert haben, können Sie von einem Internet Browser, der auf einem beliebigen Computer in der Firewall Ihrer Organisation ausgeführt wird, auf die lync Server 2013-Systemsteuerung zugreifen. Details zum Konfigurieren der einfachen URL für die Verwaltung finden Sie unter <A href="lync-server-2013-planning-for-simple-urls.md">Planen einfacher URLs in lync Server 2013</A> in der Planungsdokumentation und <A href="lync-server-2013-edit-or-configure-simple-urls.md">Bearbeiten oder konfigurieren einfacher URLs in lync Server 2013</A> in der Bereitstellungsdokumentation.

    
    </div>

2.  Öffnen Sie ein Browserfenster, und geben Sie dann die für Ihre Organisation konfigurierte Administrator-URL ein.

</div>

<div>

## <a name="to-open-lync-server-2013-control-panel-on-a-computer-running-lync-server-2013"></a>So öffnen Sie die lync Server 2013-Systemsteuerung auf einem Computer mit lync Server 2013

1.  Melden Sie sich bei einem Benutzerkonto, das Mitglied der Rolle CsAdministrator oder einer anderen Rolle ist, die über die entsprechenden Benutzerrechte und Berechtigungen für die auszuführende Aufgabe verfügt, an einem Computer an, auf dem Sie lync Server 2013 installiert haben, oder zumindest die lync Server 2013-Verwaltung. Ive-Tools. Zum Konfigurieren der Einstellungen muss der Computer mindestens eine Bildschirmauflösung von 1024 x 768 aufweisen.

2.  Starten Sie die lync Server 2013-Systemsteuerung: Klicken Sie auf **Start**, klicken Sie auf **Alle Programme**, zeigen Sie auf **Verwaltung**, zeigen Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server 2013-System**Steuerung.

</div>

</div>

<span id="BKMK_OpenManagementShell"></span>

<div>

## <a name="lync-server-2013-management-shell"></a>Verwaltungsshell für Lync Server 2013

Gehen Sie wie folgt vor, um die lync Server 2013-Verwaltungsshell zum Verwalten von Servern, Benutzern, Clients und Geräten in Ihrer Umgebung über die Befehlszeile zu öffnen.

<div>


> [!NOTE]  
> Sie können ein Benutzerkonto verwenden, das der CsAdministrator-Rolle zugewiesen ist, um eine beliebige Aufgabe in der lync Server 2013-Verwaltungsshell auszuführen. Sie können sich mit anderen Rollen anmelden, um bestimmte Verwaltungsaufgaben auszuführen, abhängig von der Aufgabe, die Sie ausführen müssen. So können Sie beispielsweise CSArchivingAdministrator verwenden, um Cmdlets für die Archivierungsverwaltung auszuführen. Details zu Rollen finden Sie unter <A href="lync-server-2013-planning-for-role-based-access-control.md">Planen der rollenbasierten Zugriffssteuerung in lync Server 2013</A> in der Planungsdokumentation. Details zu den Rollen, die Sie zum Ausführen eines bestimmten Cmdlets verwenden können, finden Sie in der Dokumentation für das Cmdlet.<BR>Sie können bestimmte Cmdlets auch ausführen, indem Sie je nach Cmdlet ein Benutzerkonto in den Gruppen RTCUniversalServerAdmins, RTCUniversalUserAdmins oder RTCUniversalReadOnlyAdmins verwenden.



</div>

<div>

## <a name="to-open-the-lync-server-2013-management-shell"></a>So öffnen Sie die lync Server 2013-Verwaltungsshell

  - Wenn Sie ein Windows PowerShell-Fenster anstelle der lync Server 2013-Verwaltungsshell öffnen, können die lync Server 2013-Cmdlets standardmäßig nicht ausgeführt werden. Wenn Sie die lync Server 2013-Cmdlets in Windows PowerShell ausführen möchten, geben Sie Folgendes an der Windows PowerShell-Eingabeaufforderung ein:
    
    `Import-Module Lync`

  - Starten Sie die lync Server-Verwaltungsshell: Klicken Sie auf **Start**, klicken Sie auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server-Verwaltungsshell**.

</div>

</div>

<div>

## <a name="see-also"></a>Siehe auch


[Installieren von Lync Server 2013-Verwaltungstools](lync-server-2013-install-lync-server-administrative-tools.md)  


[Lync Server 2013-Verwaltungstools](lync-server-2013-lync-server-administrative-tools.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

