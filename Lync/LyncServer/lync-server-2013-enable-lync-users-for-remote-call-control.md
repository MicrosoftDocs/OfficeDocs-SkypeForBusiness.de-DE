---
title: 'Lync Server 2013: Aktivieren von Lync-Benutzern für die Remoteanrufsteuerung'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Enable Lync users for remote call control
ms:assetid: f39bc10d-034c-4875-a0b8-554e1109e7e6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615048(v=OCS.15)
ms:contentKeyID: 48185795
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c6eae16d6dae46bab4f6cf745bc2e2a827eabcb3
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34832314"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enable-lync-users-for-remote-call-control-in-lync-server-2013"></a>Aktivieren von Lync-Benutzern für die Remoteanrufsteuerung in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-09-21_

Sie können lync-Benutzer für die Remoteanrufsteuerung konfigurieren, indem Sie in-Band-Bereitstellungsrichtlinien verwenden, die Server basiert sind. Sie können in-Band-Bereitstellungseinstellungen mithilfe der lync Server-Systemsteuerung oder der Befehlszeilenschnittstelle der lync Server-Verwaltungsshell verwalten. Diese Tools ersetzen das WMI-Snap-in (Windows Management Instrumentation), das zum Verwalten von Gruppenrichtlinieneinstellungen in früheren Versionen verwendet wurde.

Wenn Sie es vorziehen, Benutzern die Konfiguration eigener Einstellungen für die Remoteanrufsteuerung in lync zu ermöglichen, können Sie die Einstellungen für die Remoteanrufsteuerung für Benutzer auf dem Server konfigurieren, ohne den URI und die **URI** -Werte für den **Leitungsserver** anzugeben. Stellen Sie sicher, dass Sie Ihren Benutzern die entsprechenden URI **** -und URI-Werte für den **Leitungs Server** mitteilen, und geben Sie Ihren Benutzern die Anweisungen zum Konfigurieren dieser Einstellungen. Das Verfahren zum manuellen Konfigurieren der Remoteanrufsteuerung in lync Server finden Sie unter "Festlegen von Telefonoptionen und- <http://go.microsoft.com/fwlink/p/?linkid=210132> Nummern" in der lync-Client Dokumentation auf der Microsoft Office-Website.

Wenn Sie über eine vorhandene Communications Server 2007 R2-oder Communications Server 2007-Bereitstellung verfügen, verwenden Communicator 2007 R2-und Communicator 2007-Clients weiterhin Gruppenrichtlinien während der parallelen Migration. Wenn die Richtlinieneinstellungen jedoch auf lync-Clients übertragen werden sollen, müssen Sie die entsprechenden Einstellungen für lync Server-in-Band-Bereitstellung konfigurieren.

<div>


> [!NOTE]  
> Um einen Benutzer für die Remoteanrufsteuerung zu aktivieren, müssen Sie den Benutzer mit einem Leitungs-URI und einem Leitungs Server-URI versorgen. Wie unter <A href="lync-server-2013-deployment-tasks-for-remote-call-control.md">Bereitstellungsaufgaben für die Remoteanrufsteuerung in lync Server 2013</A>beschrieben, müssen Sie sicherstellen, dass Sie die Syntax verwenden, die für das Gateway für diese Einstellungen erforderlich ist.<BR>Stellen Sie sicher, dass die Domäne im Linien Server-URI mit der Zieldomäne identisch ist, die Sie im MatchUri-Parameter angegeben haben, als Sie die statische Route zum Gateway konfiguriert haben.<BR>Der Zeile-URI gibt die Telefonnummer an, die dem Benutzer im E. 164-Format mit dem Präfix "Tel:" zugewiesen wurde (beispielsweise Tel: + 14255550150). Wenn Sie eine Durchwahlnummer konfigurieren möchten, lautet das Format Tel: + 14255550150; ext = 111. Wenn Sie zuvor den URI des Benutzers konfiguriert haben und sich der Wert nicht geändert hat, müssen Sie den URI nicht angeben, wenn Sie den Benutzer für die Remoteanrufsteuerung aktivieren.



</div>

<div>

## <a name="to-enable-remote-call-control-for-lync-enabled-users-by-using-management-shell"></a>So aktivieren Sie die Remoteanrufsteuerung für lync-fähige Benutzer mithilfe der Verwaltungsshell

1.  Melden Sie sich bei einem Computer an, auf dem die lync Server-Verwaltungsshell als Mitglied der RTCUniversalServerAdmins-Gruppe oder als rollenbasierte zugriffssteuerungsrolle installiert ist, der Sie das Cmdlet " **Satz-CsUser** " zugewiesen haben.

2.  Starten Sie die lync Server-Verwaltungsshell: Klicken Sie auf **Start**, klicken Sie auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server-Verwaltungsshell**.

3.  Gehen Sie wie folgt vor, um das Cmdlet " **CsUser** " zum Konfigurieren der Remoteanrufsteuerung für einen vorhandenen lync-fähigen Benutzer zu verwenden:
    
        Set-CsUser -Identity <User ID> -EnterpriseVoiceEnabled $false -LineServerUri <SIP URI of the SIP/CSTA gateway> -LineUri <TEL URI of the user> -RemoteCallControlTelephonyEnabled $true
    
    Beispiel:
    
        Set-CsUser -Identity "Katie Jordan" -EnterpriseVoiceEnabled $false -LineServerUri sip:rccgateway@contoso.net -LineUri tel:+14255550150 -RemoteCallControlTelephonyEnabled $true

</div>

<div>

## <a name="to-configure-users-for-remote-call-control-by-using-lync-server-control-panel"></a>So konfigurieren Sie Benutzer für die Remoteanrufsteuerung mithilfe der lync Server-Systemsteuerung

1.  Melden Sie sich mit einem Benutzerkonto, dem die Rolle "CsUserAdministrator" oder "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.

2.  Öffnen Sie ein Browserfenster, und geben Sie dann die Administrator-URL ein, um die lync Server-Systemsteuerung zu öffnen. Details zu den verschiedenen Methoden, die Sie zum Starten der lync Server-Systemsteuerung verwenden können, finden Sie unter [Öffnen von lync Server 2013-Verwaltungstools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Klicken Sie in der linken Navigationsleiste auf **Benutzer**.

4.  Geben Sie im Feld **Benutzer suchen** alle (oder den ersten Teil) des Anzeigenamens, des Vornamens, des Nachnamens, des SAM-Kontonamens, der SIP-Adresse oder des Uniform Resource Identifier (URI) des gewünschten Benutzerkontos ein, und klicken Sie dann auf ** Finden Sie**.

5.  Klicken Sie in der Tabelle auf das Benutzerkonto, das Sie ändern möchten.

6.  Klicken Sie im Menü **Bearbeiten** auf **ändern**.

7.  Führen Sie in " **Telefonie**" eine der folgenden Aktionen aus:
    
      - Klicken Sie auf **Remoteanrufsteuerung**, um die Remoteanrufsteuerung zu aktivieren, damit der Benutzer die Telefonanlage (Private Branch Exchange, PBX) von lync 2013 für PC-zu-PC-Audioanrufe und PC-zu-Telefon-Anrufe steuern kann. Geben Sie in der **Zeile URI**die Telefonnummer des Benutzers an. Geben Sie in der **Zeile Server-URI**den SIP-URI des SIP/CSTA-Gateways an.
    
      - Um die Remoteanrufsteuerung zu aktivieren, aber PC-zu-PC-Audioanrufe zu deaktivieren und nur dem Benutzer die Steuerung seines PBX-Telefons von lync 2013 zu ermöglichen, um PC-zu-Telefon-Anrufe zu tätigen, klicken Sie **nur auf Remoteanrufsteuerung**. Geben Sie in der **Zeile URI**die Telefonnummer des Benutzers an. Geben Sie in der **Zeile Server-URI**den SIP-URI des SIP/CSTA-Gateways an.

8.  Klicken Sie abschließend auf **Commit**.

</div>

</div>

<span> </span>

</div>

</div>

</div>

