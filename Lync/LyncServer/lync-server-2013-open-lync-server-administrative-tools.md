---
title: 'Lync Server 2013: Öffnen lync Server Verwaltungstools'
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
ms.openlocfilehash: 172d448b3967782226335a5a3b9a4066514b7a9b
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/21/2020
ms.locfileid: "42216642"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="open-lync-server-2013-administrative-tools"></a>Öffnen lync Server 2013 Verwaltungstools

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-06-28_

Sie können die Verfahren in diesem Thema verwenden, um administrative Tools für die Bereitstellung, Konfiguration oder Problembehandlung Ihrer lync Server 2013 Topologie zu öffnen.

  - Bereitstellungs-Assistent

  - Topologie-Generator

  - Lync Server-Systemsteuerung

  - Lync Server-Verwaltungsshell

<span id="BKMK_OpenDeploymentWizard"></span>

<div>

## <a name="deployment-wizard"></a>Bereitstellungs-Assistent

Verwenden Sie das folgende Verfahren, um den Bereitstellungs-Assistenten lokal zu starten, um lync Server 2013-Komponentendateien hinzuzufügen oder zu entfernen.

<div>

## <a name="to-start-lync-server-2013-deployment-wizard"></a>So starten Sie den lync Server 2013-Bereitstellungs-Assistenten

1.  Melden Sie sich an dem Computer an, auf dem der lync Server-Bereitstellungs-Assistent als Mitglied der Gruppe "Domänen-Admins" und der Gruppe "RTCUniversalServerAdmins" installiert ist.

2.  Klicken Sie im **Startmenü**auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server Bereitstellungs-Assistent**.

</div>

</div>

<span id="BKMK_OpenTopologyBuilder"></span>

<div>

## <a name="topology-builder"></a>Topologie-Generator

Verwenden Sie das folgende Verfahren, um den Topologie-Generator zu öffnen, um die Server zu definieren, die Sie in ihrer lync Server 2013 Topologie bereitstellen möchten.

<div>

## <a name="to-open-lync-server-2013-topology-builder-to-design-the-topology"></a>So öffnen Sie lync Server 2013 Topologie-Generator zum Entwerfen der Topologie

1.  Melden Sie sich auf dem Computer, auf dem der Topologie-Generator installiert ist, als Mitglied der Gruppe "Domänen-Admins" oder "RTCUniversalServerAdmins" an.
    
    <div>
    

    > [!NOTE]  
    > Sie können eine Topologie mithilfe eines Kontos definieren, das Mitglied der lokalen Benutzergruppe ist, aber zum Lesen, veröffentlichen oder Aktivieren einer Topologie, die zum Installieren von lync Server 2013 auf einem Server erforderlich ist, müssen Sie ein Konto verwenden, das Mitglied der Gruppe "Domänen-Admins" und der RTCUniv ersalServerAdmins-Gruppe mit Vollzugriff auf die Dateifreigabe, die Sie für den Archivierungsdatei Speicher verwenden möchten (also lesen, schreiben und ändern), damit der Topologie-Generator die erforderliche DACL (Discretionary Access Control List) konfigurieren kann. oder ein Konto mit gleichwertigen Benutzerrechten.

    
    </div>

2.  Starten Sie den Topologie-Generator: Klicken Sie im **Startmenü**auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server Topologie-Generator**.

</div>

</div>

<span id="BKMK_OpenControlPanel"></span>

<div>

## <a name="lync-server-2013-control-panel"></a>Lync Server 2013-Systemsteuerung

Verwenden Sie eines der folgenden Verfahren, um lync Server 2013-Systemsteuerung zu öffnen, um die Konfiguration von Servern, Benutzern, Clients und Geräten in Ihrer Umgebung zu verwalten.

<div>


> [!NOTE]  
> Sie können ein Benutzerkonto verwenden, das der CsAdministrator-Rolle zugewiesen ist, um eine beliebige Aufgabe in lync Server 2013 Systemsteuerung auszuführen. Sie können andere Rollen zur Anmeldung bei lync Server 2013 Systemsteuerung verwenden, um bestimmte Verwaltungsaufgaben auszuführen, abhängig von der Aufgabe, die Sie ausführen müssen. Beispielsweise können Sie csarchivingadministrator "zur Verwaltung der Archivierung in lync Server 2013 Systemsteuerung verwenden. Ausführliche Informationen zu Rollen finden Sie unter <A href="lync-server-2013-planning-for-role-based-access-control.md">Planen der rollenbasierten Zugriffssteuerung in lync Server 2013</A> in der Planungsdokumentation. Ausführliche Informationen zu den Rollen, die Sie zum Ausführen einer bestimmten Aufgabe verwenden können, finden Sie in der Dokumentation für den Vorgang.



</div>

<div>

## <a name="to-open-lync-server-2013-control-panel-from-any-computer-inside-your-organizations-firewall"></a>So öffnen Sie lync Server 2013 Systemsteuerung von einem beliebigen Computer innerhalb der Firewall Ihres Unternehmens

1.  Melden Sie sich von einem Benutzerkonto, das der CsAdministrator-Rolle oder einer anderen Rolle zugewiesen ist, die über entsprechende Benutzerrechte und Berechtigungen für die auszuführende Aufgabe verfügt, bei einem beliebigen Computer in ihrer internen Bereitstellung mit einer minimalen Bildschirmauflösung von 1024 x 768 an.
    
    <div>
    

    > [!IMPORTANT]  
    > Wenn Sie einen einfachen Verwaltungs-URL (Uniform Resource Locator) konfiguriert haben, können Sie über einen Internet Browser, der auf einem beliebigen Computer in der Firewall Ihrer Organisation läuft, auf lync Server 2013 Systemsteuerung zugreifen. Ausführliche Informationen zum Konfigurieren der einfachen Verwaltungs-URL finden Sie unter <A href="lync-server-2013-planning-for-simple-urls.md">Planning for Simple URLs in lync Server 2013</A> in der Dokumentation zur Planung und <A href="lync-server-2013-edit-or-configure-simple-urls.md">Bearbeiten oder konfigurieren einfacher URLs in lync Server 2013</A> in der Bereitstellungsdokumentation.

    
    </div>

2.  Öffnen Sie ein Browserfenster, und geben Sie die für Ihre Organisation konfigurierte Admin-URL ein.

</div>

<div>

## <a name="to-open-lync-server-2013-control-panel-on-a-computer-running-lync-server-2013"></a>So öffnen Sie lync Server 2013 Systemsteuerung auf einem Computer mit lync Server 2013

1.  Melden Sie sich bei einem Benutzerkonto, das Mitglied der CsAdministrator-Rolle oder einer anderen Rolle mit entsprechenden Benutzerrechten und Berechtigungen für die auszuführende Aufgabe ist, an einem Computer an, auf dem Sie lync Server 2013 installiert haben, oder mindestens im lync Server 2013 Verwaltung. Ive-Tools. Zum Konfigurieren von Einstellungen muss der Computer eine minimale Bildschirmauflösung von 1024 x 768 aufweisen.

2.  Start lync Server 2013 Systemsteuerung: Klicken Sie auf **Start**, klicken Sie auf **Alle Programme**, dann auf **Verwaltung**, dann auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server 2013 System**Steuerung.

</div>

</div>

<span id="BKMK_OpenManagementShell"></span>

<div>

## <a name="lync-server-2013-management-shell"></a>Lync Server 2013 Management-Shell

Verwenden Sie das folgende Verfahren, um lync Server 2013 Verwaltungsshell zum Verwalten von Servern, Benutzern, Clients und Geräten in Ihrer Umgebung mithilfe der Befehlszeile zu öffnen.

<div>


> [!NOTE]  
> Sie können ein Benutzerkonto verwenden, das der CsAdministrator-Rolle zugewiesen ist, um eine beliebige Aufgabe in lync Server 2013 Verwaltungsshell auszuführen. Sie können sich mit anderen Rollen anmelden, um bestimmte Verwaltungsaufgaben auszuführen, abhängig von der Aufgabe, die Sie ausführen müssen. Beispielsweise können Sie csarchivingadministrator "verwenden, um Cmdlets im Zusammenhang mit der Archivierungsverwaltung auszuführen. Ausführliche Informationen zu Rollen finden Sie unter <A href="lync-server-2013-planning-for-role-based-access-control.md">Planen der rollenbasierten Zugriffssteuerung in lync Server 2013</A> in der Planungsdokumentation. Ausführliche Informationen zu den Rollen, die Sie zum Ausführen eines bestimmten Cmdlets verwenden können, finden Sie in der Dokumentation für das Cmdlet.<BR>Sie können auch bestimmte Cmdlets mithilfe eines Benutzerkontos in den Gruppen RTCUniversalServerAdmins, RTCUniversalUserAdmins oder RTCUniversalReadOnlyAdmins ausführen, abhängig vom Cmdlet.



</div>

<div>

## <a name="to-open-the-lync-server-2013-management-shell"></a>So öffnen Sie die lync Server 2013 Management-Shell

  - Wenn Sie ein Windows PowerShell Fenster anstelle der lync Server 2013-Verwaltungsshell öffnen, können Sie die lync Server 2013-Cmdlets standardmäßig nicht ausführen. Geben Sie an der Windows PowerShell-Eingabeaufforderung Folgendes ein, um die lync Server 2013-Cmdlets in Windows PowerShell auszuführen:
    
    `Import-Module Lync`

  - Starten Sie die lync Server-Verwaltungsshell: Klicken Sie auf **Start**, dann auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server-Verwaltungsshell**.

</div>

</div>

<div>

## <a name="see-also"></a>Siehe auch


[Installieren von lync Server 2013 Verwaltungstools](lync-server-2013-install-lync-server-administrative-tools.md)  


[Lync Server 2013 Verwaltungstools](lync-server-2013-lync-server-administrative-tools.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

