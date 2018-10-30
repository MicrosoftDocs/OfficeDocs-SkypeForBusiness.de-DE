---
title: Zuweisen einer Wählplanrichtlinie auf Benutzerebene
TOCTitle: Zuweisen einer Wählplanrichtlinie auf Benutzerebene
ms:assetid: 9fea861f-7770-4cae-9b1f-2a960595bfc9
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ688156(v=OCS.15)
ms:contentKeyID: 49890864
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Zuweisen einer Wählplanrichtlinie auf Benutzerebene

 

_**Letztes Änderungsdatum des Themas:** 2013-02-22_

Für den Abschluss der Benutzerkontokonfiguration für Benutzer von Enterprise-VoIP oder Benutzer von Einwahlkonferenzen müssen dem Benutzer Wähleinstellungen zugewiesen werden. Für die Benutzerkonten werden automatisch die globalen Wähleinstellungen verwendet oder, sofern vorhanden und Sie keine benutzerbezogenen Wähleinstellungen explizit zuweisen, die Wähleinstellungen auf Standortebene verwendet. Wenn Sie die globalen Wähleinstellungen oder den Standortwählplan für alle Benutzer verwenden möchten, die für Enterprise VoIP aktiviert sind, können Sie diesen Abschnitt überspringen.

## So weisen Sie Wähleinstellungen mit Systemsteuerung für Lync Server 2013 zu

1.  Melden Sie sich mit einem Benutzerkonto, dem die Rolle "CsUserAdministrator" oder "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.

2.  Öffnen Sie ein Browserfenster, und geben Sie die Admin-URL ein, um die Lync Server-Systemsteuerung zu öffnen. Informationen zu den verschiedenen Methoden zum Starten der Lync Server-Systemsteuerung finden Sie unter [Öffnen von Lync Server-Verwaltungstools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Klicken Sie in der linken Navigationsleiste auf **Benutzer**.

4.  Geben Sie im Feld **Benutzer suchen** einen Teil oder den vollständigen Anzeigenamen, Vornamen, Nachnamen, SAM-Kontonamen (Security Accounts Manager), die SIP-Adresse oder den Anschluss-URI (Uniform Resource Identifier) des Benutzerkontos ein, das aktiviert werden soll, und klicken Sie dann auf **Suchen**.

5.  Klicken Sie in der Tabelle auf das Benutzerkonto, dem Sie Einwähleinstellungen zuweisen möchten.

6.  Klicken Sie im Menü **Bearbeiten** auf **Details anzeigen**.

7.  Klicken Sie auf der Seite **Lync Server-Benutzer bearbeiten** unter **Telefonie** auf **Enterprise-VoIP**.

8.  Klicken Sie auf **Wählplanrichtlinie**, und wählen Sie dann die gewünschten Einwähleinstellungen aus.

9.  Klicken Sie auf **Commit**.

Einzelheiten zum Konfigurieren von Einwähleinstellungen finden Sie im Thema [Konfigurieren von Wählplänen in Lync Server 2013](lync-server-2013-configuring-dial-plans.md).

## So weisen Sie Wähleinstellungen mit Verwaltungsshell für Lync Server 2013 zu

1.  Melden Sie sich mit einem Benutzerkonto, dem die Rolle "CsUserAdministrator" oder "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.

2.  Starten der Lync Server-Verwaltungsshell: Klicken Sie auf **Start**, zeigen Sie auf **Alle Programme** und dann auf **Microsoft Lync Server 2013**, und klicken Sie anschließend auf **Lync Server-Verwaltungsshell**.

3.  Führen Sie den folgenden Befehl an der Eingabeaufforderung aus, um benutzerspezifische Wähleinstellungen zuzuweisen:
    
        Grant-CsDialPlan -Identity <UserIdParameter> -PolicyName <String>
    
    Beispiel:
    
        Grant-CsDialPlan -Identity "Bob Kelly" -PolicyName DialPlanJapan
    
    In diesem Beispiel wird dem Benutzer mit dem Anzeigenamen Bob Kelly die Benutzerwähleinstellungen mit der Bezeichnung **DialPlanJapan** zugewiesen.

Ausführliche Informationen zum Zuweisen von Benutzerwähleinstellungen oder zum Ausführen des **Grant-CsDialPlan**-Cmdlets finden Sie in der Dokumentation zur [Lync Server-Verwaltungsshell](lync-server-2013-lync-server-management-shell.md).

## Zuweisen benutzerbezogener Einwähleinstellunge mit Windows PowerShell-Cmdlets

Benutzerbezogene Einwähleinstellungen können auch mit Windows PowerShell und dem **Grant-CsdialPlan**-Cmdlet zugewiesen werden. Dieses Cmdlet kann über Verwaltungsshell für Lync Server 2013 oder über eine Remotesitzung von Windows PowerShell ausgeführt werden. Ausführliche Informationen zur Remoteverwendung von Windows PowerShell, um eine Verbindung zu einem Lync-Server herzustellen, finden Sie im Lync Server Windows PowerShell-Blog "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" unter [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).

## Zuweisen benutzerbezogener Einwähleinstellungen zu einem einzelnen Benutzer

  - Mithilfe des folgenden Befehls werden dem Benutzer Ken Myer die benutzerbezogenen Einwähleinstellungen RedmondDialPlan zugewiesen.
    
        Grant-CsDialPlan -Identity "Ken Myer" -PolicyName "RedmondDialPlan"

## Zuweisen benutzerbezogener Einwähleinstellungen zu mehreren Benutzern

  - Mithilfe dieses Befehls werden die benutzerbezogenen Einwähleinstellungen RedmondDialPlan allen Benutzern zugewiesen, die in Redmond arbeiten. Weitere Informationen zu dem in diesem Befehl verwendeten Parameter LdapFilter finden Sie in der Dokumentation des [Get-CsUser](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsUser)-Cmdlets.
    
        Get-CsUser -LdapFilter "l=Redmond" | Grant-CsDialPlan -PolicyName "RedmondDialPlan"

## Aufheben der Zuweisung benutzerbezogener Einwähleinstellungen

  - Mithilfe des folgenden Befehls wird die Zuweisung der benutzerbezogenen Einwähleinstellungen aufgehoben, die Ken Myer zuvor zugewiesen wurde. Nachdem die Zuweisung der benutzerbezogenen Einwähleinstellungen aufgehoben wurde, wird Ken Myer automatisch mithilfe der globalen Einwähleinstellungen, seines lokalen Standortwählplans (sofern vorhanden) oder mithilfe der Wähleinstellungen auf Dienstebene für seine Registrierung oder sein PSTN-Gateway verwaltet. Wähleinstellungen auf Dienstebene haben Vorrang vor jeglichen Standortwählplänen, und ein Standortwählplan hat Vorrang vor den globalen Einwähleinstellungen.
    
        Grant-CsDialPlan -Identity "Ken Myer" -PolicyName $Null

Weitere Informationen finden Sie im Hilfethema für das [Grant-CsDialPlan](https://docs.microsoft.com/en-us/powershell/module/skype/Grant-CsDialPlan)-Cmdlet.

## Siehe auch

#### Weitere Ressourcen

[Konfigurieren von Wählplänen in Lync Server 2013](lync-server-2013-configuring-dial-plans.md)  
[Benutzerkonten, die für Lync Server 2013 aktiviert sind](lync-server-2013-user-accounts-enabled-for-lync-server.md)

