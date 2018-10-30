---
title: Löschen eines Workflows
TOCTitle: Löschen eines Workflows
ms:assetid: 0469a6b8-ce1e-459b-bc3d-4c8adf2d97d5
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg520944(v=OCS.15)
ms:contentKeyID: 49293029
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Löschen eines Workflows

 

_**Letztes Änderungsdatum des Themas:** 2012-11-01_

Verwenden Sie eines der folgenden Verfahren, um einen Workflow zu löschen.

## So verwenden Sie Lync Server-Systemsteuerung zum Löschen eines Workflows

1.  Melden Sie sich als Mitglied der Gruppe "RTCUniversalServerAdmins" oder als Mitglied einer der vordefinierten Administratorrollen an, die Reaktionsgruppen unterstützen.

2.  Öffnen Sie ein Browserfenster, und geben Sie die Admin-URL ein, um die Lync Server-Systemsteuerung zu öffnen. Informationen zu den verschiedenen Methoden zum Starten der Lync Server-Systemsteuerung finden Sie unter [Öffnen von Lync Server-Verwaltungstools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Klicken Sie in der linken Navigationsleiste auf **Reaktionsgruppen** und dann auf **Workflow**.

4.  Klicken Sie auf der Seite **Workflow** auf **Workflow erstellen oder bearbeiten**.

5.  Geben Sie im Suchfeld **Dienst auswählen** einen Teil oder den vollständigen Namen des **ApplicationServer**-Diensts ein, der den zu löschenden Workflow hostet.

6.  Klicken Sie in der Liste der Dienste auf den gewünschten Dienst, und klicken Sie auf **OK**.
    

    > [!NOTE]
    > Die Webseite für die Konfigurationstool für Reaktionsgruppen wird geöffnet. Sie können die Webseite für die Konfigurationstool für Reaktionsgruppen auch direkt aus einem Webbrowser öffnen, indem Sie eine Verbindung mit <STRONG>https://<EM>&lt;Webpool-FQDN&gt;</EM>/RgsConfig</STRONG> herstellen.



7.  Suchen Sie unter **Vorhandenen Workflow verwalten** nach dem Workflow, den Sie löschen möchten, und klicken Sie anschließend unter **Aktion** auf **Löschen**.

8.  Klicken Sie auf **Ja**.

## So verwenden Sie Cmdlets zum Löschen eines Workflows

1.  Melden Sie sich als Mitglied der Gruppe "RTCUniversalServerAdmins" oder als Mitglied einer der vordefinierten Administratorrollen an, die Reaktionsgruppen unterstützen.

2.  Starten der Lync Server-Verwaltungsshell: Klicken Sie auf **Start**, zeigen Sie auf **Alle Programme** und dann auf **Microsoft Lync Server 2013**, und klicken Sie anschließend auf **Lync Server-Verwaltungsshell**.

3.  Führen Sie an der Eingabeaufforderung Folgendes aus:
    
        Get-CsRgsWorkflow -Identity <Application Server service> -Name "<name of workflow>" | Remove-CsRgsWorkflow
    
    Beispiel:
    
        Get-CsRgsWorkflow -Identity service:ApplicationServer:redmond.contoso.com -Name "Help Desk" | Remove-CsRgsWorkflow

