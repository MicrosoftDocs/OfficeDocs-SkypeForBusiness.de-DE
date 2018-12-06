---
title: Erstellen oder Ändern einer Mobilitätsrichtlinie
TOCTitle: Erstellen oder Ändern einer Mobilitätsrichtlinie
ms:assetid: fc2dfea0-2215-440d-9f4b-7c985da29211
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ721946(v=OCS.15)
ms:contentKeyID: 49891035
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Erstellen oder Ändern einer Mobilitätsrichtlinie

 

_**Letztes Änderungsdatum des Themas:** 2013-02-23_

Sie können Mobilitätsrichtlinien erstellen oder ändern, um mobilen Benutzern die Verwendung von unterstützten Mobilgeräten für Lync-Funktionen zu ermöglichen, etwa Instant Messaging (IM), Anwesenheit und Kontakte. Dazu verwenden Sie entweder die Systemsteuerung für Lync Server 2013 oder die Verwaltungsshell für Lync Server 2013

## So erstellen Sie eine Mobilitätsrichtlinie mithilfe der Lync Server-Systemsteuerung

1.  Melden Sie sich mit einem Benutzerkonto, dem die Rolle "CsUserAdministrator" oder "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.

2.  Öffnen Sie ein Browserfenster, und geben Sie die Admin-URL ein, um die Lync Server-Systemsteuerung zu öffnen. Informationen zu den verschiedenen Methoden zum Starten der Lync Server-Systemsteuerung finden Sie unter [Öffnen von Lync Server-Verwaltungstools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Klicken Sie auf der linken Navigationsleiste auf **Clients** und dann auf die Navigationsschaltfläche **Mobilitätsrichtlinie**.

4.  Klicken Sie auf der Seite **Mobilitätsrichtlinie** auf **Neu**, und führen Sie eine der folgenden Aktionen aus:
    
    1.  Zum Erstellen einer Mobilitätsrichtlinie auf Standortebene klicken Sie auf **Standortrichtlinie**, dann auf einen Standort und anschließend auf **OK**. Überprüfen Sie die Standardeinstellungen, und ändern Sie sie bei Bedarf.
    
    2.  Zum Erstellen einer Mobilitätsrichtlinie auf Benutzerebene klicken Sie auf **Benutzerrichtlinie**, und geben Sie einen Namen ein. Überprüfen Sie die Standardeinstellungen, und ändern Sie sie bei Bedarf.

5.  Klicken Sie auf **Commit**.

## So ändern Sie eine Mobilitätsrichtlinie mithilfe der Lync Server-Systemsteuerung

1.  Melden Sie sich mit einem Benutzerkonto, dem die Rolle "CsUserAdministrator" oder "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.

2.  Öffnen Sie ein Browserfenster, und geben Sie die Admin-URL ein, um die Lync Server-Systemsteuerung zu öffnen. Informationen zu den verschiedenen Methoden zum Starten der Lync Server-Systemsteuerung finden Sie unter [Öffnen von Lync Server-Verwaltungstools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Klicken Sie auf der linken Navigationsleiste auf **Clients** und dann auf die Navigationsschaltfläche **Mobilitätsrichtlinie**.

4.  Klicken Sie auf der Seite **Mobilitätsrichtlinie** auf eine der vorhandenen Mobiltätsrichtlinien.

5.  Klicken Sie im Menü **Bearbeiten** auf **Details anzeigen**.

6.  Bearbeiten Sie die betreffenden Einstellungen.

7.  Klicken Sie auf **Commit**.

## Erstellen von Mobilitätsrichtlinien mithilfe von Windows PowerShell-Cmdlets

Sie können Mobilitätsrichtlinien (auf Standort- oder Benutzerebene) auch mithilfe von Windows PowerShell und des **New-CsMobilityPolicy**-Cmdlets erstellen. Darüber hinaus können Sie das **Set-CsMobilityPolicy**-Cmdlet verwenden, um vorhandene Richtlinien zu ändern, z.\&nbsp;B. die globale Richtlinie. Diese Cmdlets können Sie entweder in der Verwaltungsshell für Lync Server 2013 ausführen oder in einer Remotesitzung von Windows PowerShell.

## Erstellen einer Mobilitätsrichtlinie auf Standortebene

  - Mit diesem Befehl wird eine neue Mobilitätsrichtlinie für den Standort Redmond erstellt:
    
        New-CsMobilityPolicy -Identity "site:Redmond"
    
    Da im vorstehenden Befehl keine Parameter angegeben wurden (außer dem obligatorischen **Identity**-Parameter), werden in den Richtlinien die Standardwerte für alle zugehörigen Eigenschaften verwendet.

## Erstellen einer Mobilitätsrichtlinie auf Benutzerebene

  - Zum Erstellen einer Mobilitätsrichtlinie auf Benutzerebene geben Sie eine eindeutige Identität für die Richtlinie an:
    
        New-CsMobilityPolicy -Identity "RedmondMobilityPolicy"

## Ändern eines einzelnen Eigenschaftswerts beim Erstellen einer Mobilitätsrichtlinie

  - Wenn Sie Richtlinien erstellen möchten, die andere Eigenschaftswerte enthalten, schließen Sie den betreffenden Parameter und Parameterwert ein. Beispielsweise wird mit dem folgenden Befehl eine Mobilitätsrichtlinie erstellt, die die Funktion zum Anrufen vom Arbeitsplatz aus deaktiviert:
    
        New-CsMobilityPolicy -Identity "site:Redmond" -EnableOutsideVoice $False

## Ändern von mehreren Eigenschaftswerten beim Erstellen einer Mobilitätsrichtlinie

  - Wenn Sie mehrere Eigenschaftswerte ändern möchten, schließen Sie mehrere Parameter ein. Beispielsweise wird mit dem folgenden Befehl eine Richtlinie erstellt, die sowohl Mobilität als auch das Anrufen vom Arbeitsplatz aus deaktiviert:
    
        New-CsMobilityPolicy "site:Redmond" -EnableMobility $False -EnableOutsideVoice $False

Ausführliche Informationen finden Sie im Hilfethema zum [New-CsMobilityPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsMobilityPolicy)- und zum [Set-CsMobilityPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsMobilityPolicy)-Cmdlet.

## Siehe auch

#### Aufgaben

[Konfigurieren der Mobilitätsrichtlinie in Lync Server 2013](lync-server-2013-configuring-mobility-policy.md)

