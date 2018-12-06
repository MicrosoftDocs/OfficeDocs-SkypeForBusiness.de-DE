---
title: Erstellen einer Archivierungsrichtlinie zum Aktivieren oder Deaktivieren der Archivierung von interner oder externer Kommunikation für bestimmte Standorte oder Benutzer
TOCTitle: Erstellen einer Archivierungsrichtlinie zum Aktivieren oder Deaktivieren der Archivierung von interner oder externer Kommunikation für bestimmte Standorte oder Benutzer
ms:assetid: 5864793a-ba72-470c-bb5b-9fb41e968896
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg398385(v=OCS.15)
ms:contentKeyID: 49294068
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Erstellen einer Archivierungsrichtlinie zum Aktivieren oder Deaktivieren der Archivierung von interner oder externer Kommunikation für bestimmte Standorte oder Benutzer

 

_**Letztes Änderungsdatum des Themas:** 2013-02-23_

Die Archivierung der internen und der externen Kommunikation von Benutzern, die in Lync Server 2013 verwaltet werden, wird in Lync Server 2013 mithilfe von Richtlinien aktiviert oder deaktiviert. Dazu gehören folgende Archivierungsrichtlinien:

  - Eine globale Richtlinie. Diese Richtlinie wird standardmäßig beim Bereitstellen von Lync Server 2013 erstellt.

  - Optionale Richtlinien auf Standort- und Benutzerebene. Diese Richtlinien können Sie erstellen und verwenden, um anzugeben, wie die Archivierung für bestimmte Benutzer oder Standorte implementiert werden soll.

Die Archivierungsrichtlinien werden zum ersten Mal beim Bereitstellen der Archivierung eingerichtet. Sie können diese Richtlinien jedoch zu einem späteren Zeitpunkt ändern, ergänzen und löschen. In Systemsteuerung für Lync Server 2013 können Sie die Richtlinien in der Gruppe **Archivierung und Überwachung** auf der Seite **Archivierungsrichtlinie** auf globaler Ebene sowie auf Standort- und Benutzerebene verwalten. Wenn Sie den Lync Server-Speicher in Ihren Exchange 2013-Speicher integrieren, haben die Exchange-Benutzerrichtlinien Vorrang gegenüber den Lync Server 2013-Archivierungsrichtlinien.

Nähere Informationen über das Implementieren von Richtlinien, einschließlich ihrer Hierarchien, finden Sie in den Planungs-, Bereitstellungs- und Betriebsdokumentationen unter [Funktionsweise der Archivierung in Lync Server 2013](lync-server-2013-how-archiving-works.md).


> [!NOTE]
> Um die Implementierung der Archivierung zu kontrollieren, müssen Sie die entsprechenden Optionen in der Archivierungskonfiguration festlegen. Beispielsweise können Sie angeben, ob Sofortnachrichten oder Konferenzen archiviert werden sollen, Sie können den kritischen Modus konfigurieren, oder Sie können die Optionen zum Löschen festlegen. In der Standardeinstellung sind weder in der globalen Archivierungskonfiguration noch in der Konfiguration für einzelne Standorte oder Pools Optionen aktiviert. Konfigurieren Sie alle erforderlichen Optionen in den Archivierungseinstellungen, bevor Sie die Archivierung aktivieren. Nähere Informationen finden Sie in der Betriebsdokumentation unter <A href="lync-server-2013-managing-archiving-configuration-options-for-your-organization-sites-and-pools.md">Verwalten von Konfigurationsoptionen für die Archivierung in Lync Server 2013 für Ihre Organisation, Standorte und Pools</A>.<BR>Wenn Sie die Microsoft Exchange-Integration für Ihre Bereitstellung aktiviert haben, legen die Exchange-Richtlinien fest, ob die Archivierung für Benutzer aktiviert ist, die in Exchange 2013 verwaltet werden und deren Postfächer sich im Compliance-Archiv befinden. Nähere Informationen finden Sie in der Bereitstellungsdokumentation unter <A href="lync-server-2013-setting-up-policies-for-archiving-when-using-exchange-server-integration.md">Einrichten von Richtlinien für die Archivierung beim Verwenden von Exchange Server-Integration</A>.



## So erstellen Sie eine Archivierungsrichtlinie für einen Standort oder für Benutzer

1.  Melden Sie sich mit einem Benutzerkonto, dem die Rolle "CsArchivingAdministrator" oder "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.

2.  Öffnen Sie ein Browserfenster, und geben Sie die Admin-URL ein, um die Lync Server-Systemsteuerung zu öffnen. Informationen zu den verschiedenen Methoden zum Starten der Lync Server-Systemsteuerung finden Sie unter [Öffnen von Lync Server-Verwaltungstools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Klicken Sie auf der linken Navigationsleiste auf **Überwachung und Archivierung** und anschließend auf **Archivierungsrichtlinie**.

4.  Klicken Sie auf **Neu**, und führen Sie einen der folgenden Schritte aus:
    
      - Um eine Archivierungsrichtlinie auf Standortebene zu erstellen, klicken Sie auf **Standortrichtlinie** und dann unter **Standort auswählen** auf den Standort, auf den die Richtlinie angewendet werden soll.
    
      - Um eine Archivierungsrichtlinie auf Benutzerebene zu erstellen, klicken Sie auf **Benutzerrichtlinie**.

5.  Führen Sie unter **Neue Archivierungsrichtlinie** die folgenden Aktionen aus:
    
      - Geben Sie unter **Name** einen Namen für die neue Richtlinie an (z. B. "externalContoso").
    
      - Geben Sie unter **Beschreibung** Einzelheiten über den Zweck der Richtlinie an (z. B. Archivierungsrichtlinie für externe Benutzer für Contoso)
    
      - Aktivieren oder deaktivieren Sie das Kontrollkästchen **Interne Kommunikation archivieren**, um die Archivierung der Kommunikation mit internen Benutzern zu aktivieren oder zu deaktivieren.
    
      - Aktivieren oder deaktivieren Sie das Kontrollkästchen **Externe Kommunikation archivieren**, um die Archivierung der externen Kommunikation zu aktivieren oder zu deaktivieren.

6.  Klicken Sie auf **Commit**.
    

    > [!IMPORTANT]
    > Die Einstellungen einer Benutzerrichtlinie wirken sich nur auf die Benutzer oder Benutzergruppen aus, auf die Sie die Richtlinie anwenden. Nähere Informationen finden Sie unter <A href="lync-server-2013-applying-an-archiving-policy-to-users.md">Anwenden einer Archivierungsrichtlinie auf Benutzer</A>



## Erstellen einer Archivierungsrichtlinie mit den Lync Server-Verwaltungsshell-Cmdlets

Archivierungsrichtlinien können auch mit Windows PowerShell und mit dem Cmdlet **Remove-CsArchivingPolicy** gelöscht werden. Dieses Cmdlet kann über Verwaltungsshell für Lync Server 2013 oder über eine Remotesitzung von Windows PowerShell ausgeführt werden. Ausführliche Informationen zur Remoteverwendung von Windows PowerShell, um eine Verbindung zu einem Lync-Server herzustellen, finden Sie im Lync Server Windows PowerShell-Blog "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" unter [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).

## Erstellen einer neuen Archivierungsrichtlinie auf Standortebene

  - Mit diesem Befehl wird eine neue Archivierungsrichtlinie für den Standort "Redmond" erstellt:
    
        New-CsArchivingPolicy -Identity "site:Redmond"

## Erstellen einer neuen Archivierungsrichtlinie auf Benutzerebene

  - Um eine neue Archivierungsrichtlinie auf Benutzerebene zu erstellen, geben Sie beim Erstellen der Richtlinie einfach eine eindeutige ID an:
    
        New-CsArchivingPolicy -Identity "RedmondArchivingPolicy"

## Erstellen einer neuen Archivierungsrichtlinie zum Aktivieren der Archivierung interner Kommunikationssitzungen

  - In den vorangehenden Befehlen wurden (mit Ausnahme des obligatorischen ID-Parameters) keine Parameter angegeben. Neue Richtlinien verwenden daher die Standardwerte für alle zugehörigen Eigenschaften. Um neue Richtlinien mit anderen Eigenschaftenwerten zu erstellen, schließen Sie einfach den erforderlichen Parameter sowie den gewünschten Wert ein. Mit dem folgenden Befehl wird beispielsweise eine Archivierungsrichtlinie erstellt, die die Archivierung interner Sofortnachrichtensitzungen ermöglicht:
    
        New-CsArchivingPolicy -Identity "site:Redmond" -ArchiveInternal $True

## Erstellen einer neuen Archivierungsrichtlinie zur Archivierung interner und externer Kommunikationssitzungen

  - Mehrere Eigenschaftenwerte können durch Einschließen mehrerer Parameter geändert werden. Mit dem folgenden Befehl wird beispielsweise eine neue Richtlinie zum Archivieren interner und externer Sofortnachrichtensitzungen konfiguriert:
    
        New-CsArchivingPolicy -Identity "site:Redmond" -ArchiveInternal $True -ArchiveExternal $True

Weitere Informationen finden Sie im Hilfethema für das [New-CsArchivingPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsArchivingPolicy)-Cmdlet.

## Siehe auch

#### Weitere Ressourcen

[Verwalten der Archivierung von interner und externer Kommunikation in Lync Server 2013](lync-server-2013-managing-the-archiving-of-internal-and-external-communications.md)

