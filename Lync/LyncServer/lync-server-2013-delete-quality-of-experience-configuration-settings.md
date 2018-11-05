---
title: Löschen von Konfigurationseinstellungen für QoE (Quality of Experience)
TOCTitle: Löschen von Konfigurationseinstellungen für QoE (Quality of Experience)
ms:assetid: fd0c4c2f-3bfb-42cb-9b6a-f0f8d5aa9e81
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg182613(v=OCS.15)
ms:contentKeyID: 49296007
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Löschen von Konfigurationseinstellungen für QoE (Quality of Experience)

 

_**Letztes Änderungsdatum des Themas:** 2013-02-23_

QoE-Metriken (Quality of Experience, Erlebnisqualität) dienen der Überwachung der Qualität von Audio- und Videoanrufen in Ihrer Organisation, z. B. der Anzahl der verloren gegangenen Netzwerkpakete, von Hintergrundgeräuschen und der Unterschiede bei Paketverzögerung (Jitter). Diese Metriken werden in einer Datenbank getrennt von anderen Daten (z. B. den Kommunikationsdatensätzen) gespeichert, sodass QoE unabhängig von anderen Datenaufzeichnungen aktiviert und deaktiviert werden kann.

Während der Installation von Microsoft Lync Server 2013 wird automatisch eine globale Auflistung der Konfigurationseinstellungen für QoE erstellt. Administratoren haben außerdem die Möglichkeit, benutzerdefinierte Auflistungen von Einstellungen zu erstellen, die auf einzelne Standorte angewendet werden können. Prinzipiell gilt, dass auf Standortebene konfigurierte Einstellungen Vorrang haben vor auf globaler Ebene konfigurierten Einstellungen. Wenn Sie Einstellungen auf Standortebene löschen, wird QoE an diesem Standort unter Verwendung der globalen Einstellungen gesteuert.

Beachten Sie, dass Sie die globalen Einstellungen auch "löschen" können. Allerdings werden die globalen Einstellungen dabei nicht wirklich entfernt. Vielmehr werden alle Eigenschaften in dieser Auflistung auf ihre Standardwerte zurückgesetzt. Ein Beispiel: Angenommen, in einer Auflistung von QoE-Konfigurationseinstellungen ist standardmäßig die Bereinigung aktiviert. Sie ändern nun die globale Auflistung dahin gehend, dass Bereinigung deaktiviert ist. Wenn Sie später die globalen Einstellungen löschen, werden alle Eigenschaften auf ihre Standardwerte zurückgesetzt. In diesem Fall bedeutet das, dass die Bereinigung wieder aktiviert ist.

Mit der Lync Server-Systemsteuerung oder dem [Remove-CsQoEConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsQoEConfiguration)-Cmdlet können Sie QoE-Konfigurationseinstellungen entfernen.

## So löschen Sie QoE-Konfigurationseinstellungen mithilfe der Lync Server-Systemsteuerung

1.  Melden Sie sich auf dem Computer als Mitglied der Gruppe "RTCUniversalServerAdmins" oder als Benutzer mit der Rolle "CsVoiceAdministrator", "CsServerAdministrator" oder "CsAdministrator" an. Ausführliche Informationen finden Sie unter [Delegieren von Setupberechtigungen in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).

2.  Öffnen Sie ein Browserfenster, und geben Sie die Admin-URL ein, um die Lync Server-Systemsteuerung zu öffnen. Informationen zu den verschiedenen Methoden zum Starten der Lync Server-Systemsteuerung finden Sie unter [Öffnen von Lync Server-Verwaltungstools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Klicken Sie in der linken Navigationsleiste auf **Überwachung und Archivierung** und dann auf **QoE-Daten**.

4.  Klicken Sie auf der Seite **QoE-Daten** auf die gewünschte Richtlinie, dann auf **Bearbeiten** und anschließend auf **Löschen**.

5.  Klicken Sie auf **OK**.

## So entfernen Sie QoE-Konfigurationseinstellungen mithilfe von Lync Server-Verwaltungsshell-Cmdlets

Sie können QoE-Konfigurationseinstellungen auch mithilfe von Lync Server-Verwaltungsshell und des **Remove-CsQoEConfiguration**-Cmdlets löschen. Dieses Cmdlet können Sie entweder in der Verwaltungsshell für Lync Server 2013 ausführen oder in einer Remotesitzung von Windows PowerShell.

## So entfernen Sie eine angegebene Auflistung von QoE-Konfigurationseinstellungen

  - Mit diesem Befehl werden die QoE-Konfigurationseinstellungen entfernt, die auf den Standort Redmond angewendet wurden:
    
        Remove-CsQoEConfiguration -Identity "site:Redmond"

## So entfernen Sie alle QoE-Konfigurationseinstellungen, die auf Standortebene angewendet wurden

  - Mit diesem Befehl werden alle QoE-Konfigurationseinstellungen entfernt, die auf Standortebene angewendet wurden:
    
        Get-CsQoEConfiguration -Filter "site:*" | Remove-CsQoEConfiguration

## So entfernen Sie alle QoE-Konfigurationseinstellungen, in denen QoE-Überwachung deaktiviert ist

  - Mit diesem Befehl werden alle QoE-Konfigurationseinstellungen entfernt, in denen die QoE-Überwachung deaktiviert wurde:
    
        Get-CsQoEConfiguration | Where-Object {$_.EnableQoE -eq $False} | Remove-CsQoEConfiguration

Ausführliche Informationen finden Sie unter [Remove-CsQoEConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsQoEConfiguration).

