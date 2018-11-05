---
title: 'Lync Server 2013: Aktivieren von Lync-Benutzern für die Remoteanrufsteuerung'
TOCTitle: Aktivieren von Lync-Benutzern für die Remoteanrufsteuerung
ms:assetid: f39bc10d-034c-4875-a0b8-554e1109e7e6
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg615048(v=OCS.15)
ms:contentKeyID: 49295888
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Aktivieren von Lync-Benutzern für die Remoteanrufsteuerung in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2016-12-08_

Sie können Lync-Benutzer mithilfe von serverbasierten In-Band-Bereitstellungsrichtlinien für die Remoteanrufsteuerung konfigurieren. Zur Verwaltung der Einstellungen für die In-Band-Bereitstellung verwenden Sie die Lync Server-Systemsteuerung oder die Befehlszeilenschnittstelle der Lync Server-Verwaltungsshell. Diese Tools ersetzen das Snap-In "Windows-Verwaltungsinstrumentation", das in früheren Versionen zur Verwaltung von Gruppenrichtlinieneinstellungen verwendet wurde.

Wenn Sie Benutzern ermöglichen möchten, die Einstellungen für die Remoteanrufsteuerung in Lync selbst zu konfigurieren, können Sie Einstellungen für die Remoteanrufsteuerung für Benutzer auf dem Server ohne die Werte **Anschlussserver-URI** und **Anschluss-URI** konfigurieren. Stellen Sie sicher, dass Sie den Benutzern die richtigen Werte für **Anschlussserver-URI** und **Anschluss-URI** sowie Anweisungen zur Konfiguration dieser Einstellungen bereitstellen. Die Vorgehensweise für die manuelle Konfiguration der Remoteanrufsteuerung in Lync Server finden Sie in "Set Phones options and numbers" unter <http://go.microsoft.com/fwlink/p/?linkid=210132> in der Lync-Clientdokumentation auf der Microsoft Office-Website.

Wenn Sie eine vorhandene Communications Server 2007 R2- oder Communications Server 2007-Bereistellung haben, verwenden Communicator 2007 R2- und Communicator 2007-Clients während der parallelen Migration weiterhin Gruppenrichtlinien. Wenn Sie jedoch Richtlinieneinstellungen auf Lync-Clients übertragen möchten, müssen Sie die entsprechenden In-Band-Bereitstellungseinstellungen von Lync Server konfigurieren.


> [!NOTE]
> Sie müssen einem Benutzer sowohl einen Anschluss-URI als auch einen Anschlussserver-URI bereitstellen, damit er Remoteanrufsteuerung nutzen kann. Verwenden Sie unbedingt die vom Gateway für diese Einstellungen benötigte Syntax, wie in <A href="lync-server-2013-deployment-tasks-for-remote-call-control.md">Bereitstellungsaufgaben für die Remoteanrufsteuerung in Lync Server 2013</A> beschrieben.<BR>Vergewissern Sie sich, dass die Domäne für den Anschlussserver-URI der während der Konfiguration der statischen Route zum Gateway im Parameter <STRONG>MatchUri</STRONG> -Parameter angegebenen Zieldomäne entspricht.<BR>Der Anschluss-URI gibt die dem Benutzer zugewiesene Rufnummer im E.164-Format mit dem Präfix "TEL:" an (zum Beispiel "tel:+14255550150"). Wenn Sie eine Durchwahlnummer konfigurieren möchten, lautet das Format "tel:+14255550150;ext=111". Wenn Sie den Anschluss-URI für den Benutzer bereits konfiguriert haben und der Wert sich nicht geändert hat, müssen Sie den Anschluss-URI nicht erneut angeben, wenn Sie die Remoteanrufsteuerung für diesen Benutzer aktivieren.



## So aktivieren Sie die Remoteanrufsteuerung für Lync-Benutzer mithilfe der Verwaltungsshell

1.  Melden Sie sich bei einem Computer mit installierter Lync Server-Verwaltungsshell als Mitglied der Gruppe **RTCUniversalServerAdmins** oder unter einer rollenbasierten Zugriffssteuerungsrolle an, der Sie das **Set-CsUser**-Cmdlet zugewiesen haben.

2.  Starten der Lync Server-Verwaltungsshell: Klicken Sie auf **Start**, zeigen Sie auf **Alle Programme** und dann auf **Microsoft Lync Server 2013**, und klicken Sie anschließend auf **Lync Server-Verwaltungsshell**.

3.  Zum Konfigurieren der Remoteanrufsteuerung für einen vorhandenen Lync-Benutzer mithilfe des Cmdlets **Set-CsUser** gehen Sie folgendermaßen vor:
    
        Set-CsUser -Identity <User ID> -EnterpriseVoiceEnabled $false -LineServerUri <SIP URI of the SIP/CSTA gateway> -LineUri <TEL URI of the user> -RemoteCallControlTelephonyEnabled $true
    
    Beispiel:
    
        Set-CsUser -Identity "Katie Jordan" -EnterpriseVoiceEnabled $false -LineServerUri sip:rccgateway@contoso.net -LineUri tel:+14255550150 -RemoteCallControlTelephonyEnabled $true

## So konfigurieren Sie Benutzer für die Remoteanrufsteuerung mithilfe der Lync Server-Systemsteuerung

1.  Melden Sie sich mit einem Benutzerkonto, dem die Rolle "CsUserAdministrator" oder "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.

2.  Öffnen Sie ein Browserfenster, und geben Sie die Admin-URL ein, um die Lync Server-Systemsteuerung zu öffnen. Informationen zu den verschiedenen Methoden zum Starten der Lync Server-Systemsteuerung finden Sie unter [Öffnen von Lync Server-Verwaltungstools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Klicken Sie in der linken Navigationsleiste auf **Benutzer** .

4.  Geben Sie im Feld **Benutzer suchen** einen Teil oder den vollständigen Anzeigenamen, Vornamen, Nachnamen, SAM-Kontonamen (Security Accounts Manager), die SIP-Adresse oder den Anschluss-URI (Uniform Resource Identifier) des gewünschten Benutzerkontos ein, und klicken Sie dann auf **Suchen** .

5.  Klicken Sie in der Tabelle auf das Benutzerkonto, das Sie ändern möchten.

6.  Klicken Sie im Menü **Bearbeiten** auf **Ändern** .

7.  Führen Sie im Abschnitt **Telefonie** eine der folgenden Aktionen aus:
    
      - Klicken Sie auf **Remoteanrufsteuerung** , um die Remoteanrufsteuerung zu aktivieren, sodass Benutzer ihr Nebenstellentelefon (PBX-Telefon) über Lync 2013 steuern können, um Audioanrufe von PC zu PC oder von PC zu Telefon zu tätigen. Geben Sie unter **Anschluss-URI** die Rufnummer des Benutzers an. Geben Sie unter **Anschlussserver-URI** den SIP-URI des SIP/CSTA-Gateways an.
    
      - Klicken Sie auf **Nur Remoteanrufsteuerung** , um die Remoteanrufsteuerung zu aktivieren, Audioanrufe von PC zu PC jedoch zu deaktivieren und nur dem Benutzer das Steuern seines Nebenstellentelefons über Lync 2013 zu ermöglichen, um Anrufe von PC zu Telefon tätigen zu können. Geben Sie unter **Anschluss-URI** die Rufnummer des Benutzers an. Geben Sie unter **Anschlussserver-URI** den SIP-URI des SIP/CSTA-Gateways an.

8.  Nachdem Sie die Eingabe beendet haben, klicken Sie auf **Commit** .

