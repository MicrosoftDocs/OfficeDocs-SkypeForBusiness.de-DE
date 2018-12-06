---
title: Ändern einer Archivierungsrichtlinie zum Aktivieren oder Deaktivieren der Archivierung von interner oder externer Kommunikation für Ihre Organisation, Standorte oder Benutzer
TOCTitle: Ändern einer Archivierungsrichtlinie zum Aktivieren oder Deaktivieren der Archivierung von interner oder externer Kommunikation für Ihre Organisation, Standorte oder Benutzer
ms:assetid: b85dc3fb-8ebd-4e3c-ac90-fc79270ac867
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg182576(v=OCS.15)
ms:contentKeyID: 49295191
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Ändern einer Archivierungsrichtlinie zum Aktivieren oder Deaktivieren der Archivierung von interner oder externer Kommunikation für Ihre Organisation, Standorte oder Benutzer

 

_**Letztes Änderungsdatum des Themas:** 2013-02-23_

In Lync Server 2013 verwenden Sie Richtlinien zum Aktivieren und Deaktivieren der Archivierung für interne und externe Kommunikation für Benutzer, die in Lync Server 2013 verwaltet werden. Dies umfasst die folgenden Archivierungsrichtlinien:

  - Eine globale Richtlinie, die standardmäßig erstellt wird, wenn Sie Lync Server 2013 bereitstellen.

  - Optionale Richtlinien auf Standort- und Benutzerebene, die Sie erstellen und verwenden können, um festzulegen, wie die Archivierung für bestimmte Standorte oder Benutzer umgesetzt wird.

Die Archivierungsrichtlinien werden von Ihnen zunächst bei der Bereitstellung der Archivierung eingerichtet. Sie können jedoch nach der Bereitstellung Richtlinien ändern, hinzufügen und löschen. In Systemsteuerung für Lync Server 2013 können Sie die Seite **Archivierungsrichtlinie** der Gruppe **Archivierung und Überwachung** verwenden, um Richtlinien auf globaler, Standort- und Benutzerebene zu verwalten. Wenn Sie Ihren Lync Server-Speicher mit Exchange 2013-Speicher integrieren, erhalten die Exchange-Benutzerrichtlinien Vorrang über die Lync Server 2013-Archivierungsrichtlinien.

Ausführliche Informationen zur Umsetzung von Richtlinien, einschließlich der Hierarchie von Richtlinien, finden Sie unter [Funktionsweise der Archivierung in Lync Server 2013](lync-server-2013-how-archiving-works.md) in der Planungs-, Bereitstellungs- oder Betriebsdokumentation.


> [!NOTE]
> Wenn Sie Microsoft Exchange-Integration für Ihre Bereitstellung aktiviert haben, kontrollieren Exchange-Richtlinien, ob die Archivierung für Benutzer aktiviert wird, die in Exchange 2013 verwaltet werden und ihre Postfächer auf "In-Place Hold" gestellt haben. Ausführliche Informationen finden Sie unter <A href="lync-server-2013-setting-up-policies-for-archiving-when-using-exchange-server-integration.md">Einrichten von Richtlinien für die Archivierung beim Verwenden von Exchange Server-Integration</A> in der Bereitstellungsdokumentation.<BR>Sie sollten alle entsprechenden Optionen in den Archivierungskonfigurationen angeben, bevor Sie die Archivierung aktivieren. Einzelheiten finden Sie unter <A href="lync-server-2013-managing-archiving-configuration-options-for-your-organization-sites-and-pools.md">Verwalten von Konfigurationsoptionen für die Archivierung in Lync Server 2013 für Ihre Organisation, Standorte und Pools</A> in der Betriebsdokumentation.



## So ändern Sie eine Archivierungsrichtlinie

1.  Melden Sie sich mit einem Benutzerkonto, dem die Rolle "CsArchivingAdministrator" oder "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.

2.  Öffnen Sie ein Browserfenster, und geben Sie die Admin-URL ein, um die Lync Server-Systemsteuerung zu öffnen. Informationen zu den verschiedenen Methoden zum Starten der Lync Server-Systemsteuerung finden Sie unter [Öffnen von Lync Server-Verwaltungstools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Klicken Sie auf der linken Navigationsleiste auf **Überwachung und Archivierung** und anschließend auf **Archivierungsrichtlinie**.

4.  Führen Sie in der Liste der Richtlinie einen der folgenden Schritte aus:
    
      - Klicken Sie in der Liste der Richtlinien auf **Global**, klicken Sie auf **Bearbeiten** und anschließend auf **Details anzeigen**, um die Richtlinie für Ihre gesamte Bereitstellung zu ändern.
    
      - Um die Richtlinie für einen einzelnen Standort zu ändern, klicken Sie in der Liste der Richtlinien auf den Standortnamen, klicken Sie auf **Bearbeiten**, und klicken Sie dann auf **Details anzeigen**.
    
      - Um die Richtlinie für einen einzelnen Benutzer oder eine Benutzergruppe zu ändern, klicken Sie in der Liste der Richtlinien auf den Benutzer- oder Gruppennamen, klicken Sie auf **Bearbeiten**, und klicken Sie dann auf **Details anzeigen**.

5.  Führen Sie auf der Seite **Bearbeiten der Archivierungsrichtlinie** die folgenden Aktionen aus:
    
      - Aktivieren oder deaktivieren Sie das Kontrollkästchen **Interne Kommunikation archivieren**, um die interne Archivierung für die Richtlinie zu aktivieren oder zu deaktivieren.
    
      - Aktivieren oder deaktivieren Sie das Kontrollkästchen **Externe Kommunikation archivieren**, um die externe Archivierung für die Bereitstellung zu aktivieren oder zu deaktivieren.

6.  Klicken Sie auf **Commit**.
    

    > [!IMPORTANT]
    > Die Einstellungen einer Benutzerrichtlinie gelten nur für bestimmte Benutzer und Benutzergruppen, auf die Sie die Richtlinie anwenden. Ausführliche Informationen finden Sie unter <A href="lync-server-2013-applying-an-archiving-policy-to-users.md">Anwenden einer Archivierungsrichtlinie auf Benutzer</A>



## Aktivieren und Deaktivieren der Archivierung mithilfe der Lync Server-PowerShell-Cmdlets

Die Archivierung (sowohl für interne als auch für externe Kommunikationssitzungen) kann auch mithilfe des **Set-CsArchivingPolicy**-Cmdlets aktiviert und deaktiviert werden. Dieses Cmdlet kann entweder über Verwaltungsshell für Lync Server 2013 oder über eine Remotesitzung von Windows PowerShell ausgeführt werden. Ausführliche Informationen zur Remoteverwendung von Windows PowerShell, um eine Verbindung zu einem Lync-Server herzustellen, finden Sie im Lync Server Windows PowerShell-Blog "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" unter [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).

## Aktivieren der Archivierung für interne Kommunikationssitzungen

  - Setzen Sie den Wert der **ArchiveInternal**-Eigenschaft auf "True ($True)", um die Archivierung von internen Kommunikationssitzungen zu aktivieren. Zum Beispiel:
    
        Set-CsArchivingPolicy -Identity "global" -ArchiveInternal $True

## Aktivieren der Archivierung für externe Kommunikationssitzungen

  - Setzen Sie den Wert der **ArchiveExternal** -Eigenschaft auf "True ($True)", um die Archivierung von externen Kommunikationssitzungen zu aktivieren. Zum Beispiel:
    
        Set-CsArchivingPolicy -Identity "global" -ArchiveExternal $True

## Aktivieren der Archivierung für interne und externe Kommunikationssitzungen

  - Setzen Sie die Werte für die Eigenschaften **ArchiveInternal** und **ArchiveExternal** auf "True", um die Archivierung sowohl für interne als auch für externe Kommunikationssitzungen zu aktivieren:
    
        Set-CsArchivingPolicy -Identity "global" -ArchiveInternal $True -ArchiveExternal $True

## Archivierung deaktivieren

  - Setzen Sie die Werte für die Eigenschaften **ArchiveInternal** und **ArchiveExternal** auf "False ($False)", um die Archivierung vollständig zu deaktivieren. Zum Beispiel:
    
        Set-CsArchivingPolicy -Identity "global" -ArchiveInternal $False -ArchiveExternal $False

Weitere Informationen finden Sie im Hilfethema für das [Set-CsArchivingPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsArchivingPolicy)-Cmdlet.

## Siehe auch

#### Weitere Ressourcen

[Verwalten der Archivierung von interner und externer Kommunikation in Lync Server 2013](lync-server-2013-managing-the-archiving-of-internal-and-external-communications.md)

