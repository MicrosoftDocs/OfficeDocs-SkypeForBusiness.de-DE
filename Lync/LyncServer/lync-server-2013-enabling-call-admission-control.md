---
title: Aktivieren der Anrufsteuerung
TOCTitle: Aktivieren der Anrufsteuerung
ms:assetid: 015f5c8f-2f90-4b9e-8149-b33767e90582
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg520942(v=OCS.15)
ms:contentKeyID: 49292982
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Aktivieren der Anrufsteuerung

 

_**Letztes Änderungsdatum des Themas:** 2012-11-01_

Bei der Anrufsteuerung handelt es sich um ein Netzwerk aus Regionen, Standorten und Subnetzen, mit dem Sie basierend auf der verfügbaren Bandbreite Einschränkungen für Audio- und Videoübertragungen festlegen können. Nach der Konfiguration des Anrufsteuerungsnetzwerks müssen Sie die Anrufsteuerung aktivieren, um die Bandbreiteneinschränkungen zu erzwingen. Dieser Schritt kann über die Lync Server-Systemsteuerung ausgeführt werden.

## So aktivieren Sie die Anrufsteuerung über die Lync Server-Systemsteuerung

1.  Melden Sie sich mit einem Benutzerkonto, das Mitglied der Gruppe "RTCUniversalServerAdmins" ist (oder über gleichwertige Benutzerrechte verfügt) oder dem die Rolle "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.

2.  Öffnen Sie ein Browserfenster, und geben Sie die Admin-URL ein, um die Lync Server-Systemsteuerung zu öffnen. Informationen zu den verschiedenen Methoden zum Starten der Lync Server-Systemsteuerung finden Sie unter [Öffnen von Lync Server-Verwaltungstools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Klicken Sie in der linken Navigationsleiste auf **Netzwerkkonfiguration** und dann auf **Global**.

4.  Klicken Sie auf der Seite **Global** auf die Konfiguration **Global**.
    

    > [!NOTE]
    > Da für jede Microsoft Lync Server 2013-Bereitstellung nur ein Netzwerk konfiguriert werden kann, werden in der Liste nie mehrere Netzwerkkonfigurationen angezeigt. Die globale Konfiguration kann nicht umbenannt werden.



5.  Klicken Sie im Menü **Bearbeiten** auf **Details anzeigen**.

6.  Aktivieren Sie auf der Seite **Globale Einstellungen bearbeiten** das Kontrollkästchen **Anrufsteuerung aktivieren**, und klicken Sie auf **Commit**.

Beim Klicken auf **Commit** wird die Konfiguration getestet. Das Dialogfeld **Globale Einstellungen bearbeiten** wird geschlossen, und die Seite **Global** wird erneut angezeigt. Wenn in Ihrer Netzwerkkonfiguration Fehler oder Inkonsistenzen ermittelt werden, die eine ordnungsgemäße Funktionsweise verhindern, wird eine Warnung angezeigt (wenn die einzelnen Regionen beispielsweise nicht über eine regionenübergreifende Route miteinander verbunden sind).

Nach dem Ändern Ihrer Netzwerkkonfiguration können Sie die Überprüfung erneut ausführen, indem Sie die globale Konfiguration öffnen und auf **Commit** klicken. Es ist nicht erforderlich, die Anrufsteuerung zunächst zu deaktivieren: Lassen Sie das Kontrollkästchen aktiviert, und klicken Sie auf **Commit**. Dieser Vorgang kann zu einem beliebigen Zeitpunkt ausgeführt werden, ohne Konfigurationsänderungen vorzunehmen.

## Siehe auch

#### Konzepte

[Übersicht über die Anrufsteuerung in Lync Server 2013](lync-server-2013-overview-of-call-admission-control.md)  

#### Weitere Ressourcen

[Planen des Anrufsteuerungsdiensts in Lync Server 2013](lync-server-2013-planning-for-call-admission-control.md)  
[Konfigurieren der Anrufsteuerung in Lync Server 2013](lync-server-2013-configure-call-admission-control.md)  
[Get-CsNetworkConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsNetworkConfiguration)  
[Set-CsNetworkConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsNetworkConfiguration)  
[Remove-CsNetworkConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsNetworkConfiguration)

