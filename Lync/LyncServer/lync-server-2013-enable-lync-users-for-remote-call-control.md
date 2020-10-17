---
title: 'Lync Server 2013: Aktivieren von lync-Benutzern für die Remoteanrufsteuerung'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enable Lync users for remote call control
ms:assetid: f39bc10d-034c-4875-a0b8-554e1109e7e6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615048(v=OCS.15)
ms:contentKeyID: 48185795
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 37d5aa0b9f13f17dee91ff48048908cde3dbc2cf
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2020
ms.locfileid: "48528732"
---
# <a name="enable-lync-users-for-remote-call-control-in-lync-server-2013"></a>Aktivieren von lync-Benutzern für die Remoteanrufsteuerung in lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-09-21_

Sie können lync-Benutzer für die Remoteanrufsteuerung mithilfe von in-Band-Bereitstellung-Richtlinien konfigurieren, die Server basiert sind. Sie können die Einstellungen für die in-Band-Konfiguration mithilfe von lync Server-Systemsteuerung oder der lync Server-Verwaltungsshell Befehlszeilenschnittstelle verwalten. Diese Tools ersetzen das WMI-Snap-in (Windows Management Instrumentation), das zum Verwalten von Gruppenrichtlinieneinstellungen in früheren Versionen verwendet wurde.

Wenn Sie es vorziehen, Benutzern die Konfiguration Ihrer eigenen Einstellungen für die Remoteanrufsteuerung in lync zu ermöglichen, können Sie die Einstellungen für die Remoteanrufsteuerung für Benutzer auf dem Server konfigurieren, ohne den URI und die Werte für den **Anschluss** - **URI** anzugeben. Stellen Sie sicher, dass Sie den entsprechenden **Anschluss Server-URI** und die Werte für den **Anschluss-URI** Ihren Benutzern mitteilen, und geben Sie den Benutzern Anweisungen zum Konfigurieren dieser Einstellungen. Informationen zum manuellen Konfigurieren der Remoteanrufsteuerung in lync Server finden Sie unter "Festlegen von Telefonnummern" in <https://go.microsoft.com/fwlink/p/?linkid=210132> der lync-Client Dokumentation auf der Microsoft Office Website.

Wenn Sie über eine vorhandene Communications Server 2007 R2-oder Communications Server 2007-Bereitstellung verfügen, verwenden Communicator 2007 R2 und Communicator 2007 Clients weiterhin Gruppenrichtlinien während der parallelen Migration. Wenn Sie jedoch möchten, dass Richtlinieneinstellungen auf lync-Clients übertragen werden, müssen Sie die entsprechenden lync Server Einstellungen für die in-Band-Konfiguration konfigurieren.

<div>


> [!NOTE]  
> Wenn Sie einen Benutzer für die Remoteanrufsteuerung aktivieren möchten, müssen Sie dem Benutzer sowohl einen Anschluss-URI als auch einen Anschluss Server-URI bereitstellen. Wie unter <A href="lync-server-2013-deployment-tasks-for-remote-call-control.md">Bereitstellungsaufgaben für die Remoteanrufsteuerung in lync Server 2013</A>beschrieben, müssen Sie sicherstellen, dass Sie die für das Gateway erforderliche Syntax für diese Einstellungen verwenden.<BR>Stellen Sie sicher, dass die Domäne im Linien Server-URI mit der Zieldomäne identisch ist, die Sie im Parameter MatchUri angegeben haben, als Sie die statische Route zum Gateway konfiguriert haben.<BR>Der Anschluss-URI gibt die Telefonnummer an, die dem Benutzer im E. 164-Format zugewiesen ist, mit dem Präfix "Tel:" (beispielsweise Tel: + 14255550150). Wenn Sie eine Durchwahlnummer konfigurieren möchten, lautet das Format Tel: + 14255550150; ext = 111. Wenn Sie den Anschluss-URI des Benutzers zuvor konfiguriert haben und der Wert nicht geändert wurde, müssen Sie den Anschluss-URI nicht angeben, wenn Sie den Benutzer für die Remoteanrufsteuerung aktivieren.



</div>

<div>

## <a name="to-enable-remote-call-control-for-lync-enabled-users-by-using-management-shell"></a>So aktivieren Sie die Remoteanrufsteuerung für lync-aktivierte Benutzer mithilfe von Verwaltungsshell

1.  Melden Sie sich an einem Computer an, auf dem lync Server-Verwaltungsshell als Mitglied der RTCUniversalServerAdmins-Gruppe oder als rollenbasierte zugriffssteuerungsrolle installiert ist, der Sie das Cmdlet " **CsUser** " zugewiesen haben.

2.  Starten Sie die lync Server-Verwaltungsshell: Klicken Sie auf **Start**, dann auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server-Verwaltungsshell**.

3.  Führen Sie die folgenden Schritte aus, um das Cmdlet " **CsUser** " zum Konfigurieren der Remoteanrufsteuerung für einen vorhandenen lync-aktivierten Benutzer zu verwenden:
    
        Set-CsUser -Identity <User ID> -EnterpriseVoiceEnabled $false -LineServerUri <SIP URI of the SIP/CSTA gateway> -LineUri <TEL URI of the user> -RemoteCallControlTelephonyEnabled $true
    
    Zum Beispiel:
    
        Set-CsUser -Identity "Katie Jordan" -EnterpriseVoiceEnabled $false -LineServerUri sip:rccgateway@contoso.net -LineUri tel:+14255550150 -RemoteCallControlTelephonyEnabled $true

</div>

<div>

## <a name="to-configure-users-for-remote-call-control-by-using-lync-server-control-panel"></a>So konfigurieren Sie Benutzer für die Remoteanrufsteuerung mithilfe von lync Server-Systemsteuerung

1.  Melden Sie sich mit einem Benutzerkonto, dem die Rolle CsUserAdministrator oder CsAdministrator zugewiesen ist, an einem beliebigen Computer in Ihrer internen Bereitstellung an.

2.  Öffnen Sie ein Browserfenster, und geben Sie die admin-URL ein, um das lync Server-Systemsteuerung zu öffnen. Ausführliche Informationen zu den verschiedenen Methoden, die Sie zum Starten von lync Server-Systemsteuerung verwenden können, finden Sie unter [Open lync Server 2013 Administration Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Klicken Sie in der linken Navigationsleiste auf **Benutzer**.

4.  Geben Sie im Feld **Benutzer suchen** alle (oder den ersten Teil) des Anzeigenamens, des Vornamens, des Nachnamens, des SAM-Kontonamens (Security Accounts Manager), der SIP-Adresse oder des Anschluss-URI (Uniform Resource Identifier) des gewünschten Benutzerkontos ein, und klicken Sie dann auf **Suchen**.

5.  Klicken Sie in der Tabelle auf das Benutzerkonto, das Sie ändern möchten.

6.  Klicken Sie im Menü **Bearbeiten** auf **Ändern**.

7.  Führen Sie in **Telefonie**einen der folgenden Schritte aus:
    
      - Klicken Sie auf **Remoteanrufsteuerung**, um die Remoteanrufsteuerung zu aktivieren, um dem Benutzer die Steuerung des PBX-Telefons (Private Branch Exchange) aus lync 2013 zu ermöglichen, um PC-zu-PC-Audioanrufe und PC-zu-Telefonanrufe zu tätigen. Geben Sie unter **Leitungs-URI**die Telefonnummer des Benutzers an. Geben Sie unter **Anschluss Server-URI**den SIP-URI des SIP/CSTA-Gateways an.
    
      - Um die Remoteanrufsteuerung zu aktivieren, aber PC-zu-PC-Audioanrufe zu deaktivieren und nur dem Benutzer zu ermöglichen, sein PBX-Telefon von lync 2013 zu steuern, um Anrufe von PC zu Telefon zu tätigen, klicken Sie **nur auf Remoteanrufsteuerung**. Geben Sie unter **Leitungs-URI**die Telefonnummer des Benutzers an. Geben Sie unter **Anschluss Server-URI**den SIP-URI des SIP/CSTA-Gateways an.

8.  Wenn Sie fertig sind, klicken Sie auf **Commit**.

</div>

</div>

<span> </span>

</div>

</div>

</div>

