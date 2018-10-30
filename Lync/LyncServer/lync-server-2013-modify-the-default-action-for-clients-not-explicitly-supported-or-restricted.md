---
title: Ändern der Standardaktion für Clients, die nicht explizit unterstützt werden oder für die Einschränkungen gelten
TOCTitle: Ändern der Standardaktion für Clients, die nicht explizit unterstützt werden oder für die Einschränkungen gelten
ms:assetid: 548dd0f5-62fe-4c3f-8952-2b9fd4c5fff3
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg520994(v=OCS.15)
ms:contentKeyID: 49294026
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Ändern der Standardaktion für Clients, die nicht explizit unterstützt werden oder für die Einschränkungen gelten

 

_**Letztes Änderungsdatum des Themas:** 2013-02-23_

Neben der Clientversion, die Sie in Ihrer Lync Server 2013-Umgebung unterstützen möchten, können Sie auch eine Standardaktion für Clients angeben, für die noch keine Versionsrichtlinie definiert wurde. Auf diese Weise können Sie die in Ihrer Lync Server-Umgebung verwendeten Clientversionen einschränken, sodass Sie die mit der Unterstützung mehrerer Clientversionen verbundenen Kosten kontrollieren können.

## So ändern Sie die Standardaktion für Clients, die nicht explizit unterstützt oder eingeschränkt werden

1.  Melden Sie sich mit einem Benutzerkonto, dem die Rolle "CsUserAdministrator" oder "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.

2.  Öffnen Sie ein Browserfenster, und geben Sie die Admin-URL ein, um die Lync Server-Systemsteuerung zu öffnen. Informationen zu den verschiedenen Methoden zum Starten der Lync Server-Systemsteuerung finden Sie unter [Öffnen von Lync Server-Verwaltungstools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Klicken Sie in der linken Navigationsleiste auf **Clients** und dann auf **Clientversionskonfiguration**.

4.  Doppelklicken Sie auf der Seite **Clientversionskonfiguration** auf die Konfiguration **Global** in der Liste.

5.  Stellen Sie im Dialogfeld **Clientversionskonfiguration bearbeiten** sicher, dass das Kontrollkästchen **Versionskontrolle aktivieren** aktiviert ist, und wählen Sie anschließend unter **Standardaktion** eine der folgenden Optionen aus:
    
      - **Zulassen**   Ermöglicht dem Client die Anmeldung, wenn die Clientversion keinem Filter in der Liste **Clientversionsrichtlinien** entspricht.
    
      - **Blockieren**   Verhindert die Clientanmeldung, wenn die Clientversion keinem Filter in der Liste **Clientversionsrichtlinien** entspricht.
    
      - **Blockieren mit URL**   Verhindert die Clientanmeldung, wenn die Clientversion keinem Filter in der Liste **Clientversionsrichtlinien** entspricht, und zeigt eine Fehlermeldung mit einer URL an, unter der ein neuerer Client heruntergeladen werden kann.
    
      - **Zulassen mit URL**   Lässt die Clientanmeldung zu, wenn die Clientversion keinem Filter in der Liste **Clientversionsrichtlinien** entspricht, und zeigt eine Fehlermeldung mit einer URL an, unter der ein neuerer Client heruntergeladen werden kann.

6.  Wenn Sie die Option **Blockieren mit URL** auswählen, geben Sie im Feld **URL** die URL für den Clientdownload ein, die in der Fehlermeldung angezeigt werden soll.

7.  Klicken Sie auf **Commit**.

## So deaktivieren Sie die Clientversionskontrolle

  - Um die Versionskontrolle zu deaktivieren und allen Clients unabhängig von der Clientversion die Anmeldung zu ermöglichen, deaktivieren Sie das Kontrollkästchen **Versionskontrolle aktivieren**, und klicken Sie anschließend auf **Commit**.

## Ändern der Standardaktion mit Lync Server-PowerShell-Cmdlets

Die Standardaktion für die Anmeldung von Benutzern bei Clients, die nicht explizit zugelassen oder durch eine entsprechende Richtlinie eingeschränkt sind, kann auch mit dem Cmdlet Windows PowerShell-Befehlszeilenschnittstelle und dem Cmdlet **Set-CsClientVersionPolicy** verwaltet werden. Dieses Cmdlet kann auch in der Verwaltungsshell für Lync Server 2013 oder mit einer Remotesitzung von Windows PowerShell ausgeführt werden. Ausführliche Informationen zur Remoteverwendung von Windows PowerShell, um eine Verbindung zu einem Lync-Server herzustellen, finden Sie im Lync Server Windows PowerShell-Blog "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" unter [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).

## Konfigurieren der Standardaktion zum Blockieren des Zugriffs

  - Mit dem folgenden Befehl wird die Standardaktion zum Blockieren des Standorts "Redmond" festgelegt. Dadurch wird die Registrierung für alle Clients blockiert, für die keine Konfigurationsregel bezüglich der Clientversion vorhanden ist.
    
        Set-CsClientVersionConfiguration -Identity "site:Redmond" -DefaultAction Block

## Konfigurieren der Standardaktion zum Zulassen des Zugriffs

  - In diesem Beispiel ist die Standardaktion für den Standort "Redmond" auf "Zulassen" festgelegt. Dadurch wird die Registrierung für alle Clients zugelassen, für die keine Konfigurationsregel bezüglich der Clientversion vorhanden ist.
    
        Set-CsClientVersionConfiguration -Identity "site:Redmond" -DefaultAction Allow

Weitere Informationen finden Sie im Hilfethema für das [Set-CsClientVersionPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsClientVersionPolicy)-Cmdlet.

## Siehe auch

#### Weitere Ressourcen

[Verwalten von Geräten, Telefonen und Clientanwendungen in Lync Server 2013](lync-server-2013-managing-devices-phones-and-client-applications.md)

