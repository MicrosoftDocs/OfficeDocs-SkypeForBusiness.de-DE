---
title: 'Lync Server 2013: Installieren des Planungstools'
TOCTitle: Installieren des Planungstools
ms:assetid: ebdc9e26-4b22-4b02-85b9-7462bcfe7c93
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg615046(v=OCS.15)
ms:contentKeyID: 52056485
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Installieren des Planungstools in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2013-11-07_

Bevor Sie Ihre Lync Server 2013-Infrastruktur mithilfe des Microsoft Lync Server 2013, Planungstools entwerfen und planen können, müssen Sie das Planungstool zunächst installieren. Das Planungstool muss nicht auf einer Arbeitsstation oder einem Server innerhalb der Domäne oder Infrastruktur bereitgestellt werden, in der Sie Lync Server 2013 installieren möchten. Die Infodatei zum Planungstool enthält wichtige Informationen zu Installation und Verwendung des Tools. Einige Informationen aus dieser Datei werden zur Verdeutlichung im Folgenden noch einmal aufgeführt.


> [!IMPORTANT]
> Das Planungstool muss von einem Benutzer mit Administratorrechten und -berechtigungen auf dem Computer installiert werden, auf dem das Tool verwendet werden soll.



Folgende Betriebssysteme werden für Installation und Verwendung des Planungstools unterstützt:

  - Windows 8

  - Windows 8,1

  - Windows Server 2012

  - Windows Server 2012 R2

  - Windows 7, 32-Bit-Version

  - Windows 7, 64-Bit-Version unter Verwendung von Windows on Win32 (WOW)

  - Windows Server 2008 R2 unter Verwendung von WOW

Darüber hinaus erfordert das Planungstool Microsoft .NET Framework 4.5.

Sobald die Vorinstallationsanforderungen erfüllt sind, können Sie das Planungstool installieren.

## So installieren Sie das Planungstool

1.  Melden Sie sich auf dem lokalen Computer als Mitglied der Gruppe "Administratoren" an.

2.  Suchen Sie in Windows Explorer oder in einem Befehlsfenster nach dem Verzeichnis, in das Sie die Planungstool-Installationsdateien heruntergeladen haben.

3.  Suchen Sie die Datei **LyncPlanningTool.msi** . Doppelklicken Sie in Windows-Explorer auf die Datei. Geben Sie im Befehlsfenster den Namen der Datei ein, und drücken Sie die EINGABETASTE, um die Datei auszuführen.

4.  Klicken Sie auf der Willkommensseite des Setup-Assistenten für das Microsoft Lync Server 2013-Planungstool auf **Weiter** .

5.  Lesen Sie den **Endbenutzer-Lizenzvertrag** , wählen Sie die Option **Ich stimme den Bedingungen des Lizenzvertrags zu** aus, wenn Sie die Bedingungen akzeptieren, und klicken Sie anschließend auf **Weiter** .

6.  Geben Sie an, in welchem Verzeichnis die Dateien des Planungstools installiert werden sollen. Der Standardspeicherort lautet "C:\\Programme (x86)\\Microsoft Lync Server 2013\\Planning Tool". Wenn Sie ein anderes Installationsverzeichnis auswählen möchten, klicken Sie auf **Ändern** . Navigieren Sie im Dialogfeld **Zielordner ändern** zum gewünschten Verzeichnis, oder geben Sie ein Verzeichnis ein, und klicken Sie nacheinander auf **OK** und auf **Weiter** .

7.  Das Installationsprogramm kann nun das Planungstool installieren. Klicken Sie auf **Installieren** , um den Installationsvorgang zu starten.

8.  Die Installation beginnt, und der Installationsfortschritt wird angezeigt. Klicken Sie nach Abschluss der Installation auf **Fertig stellen** .

9.  Nun können Sie das Planungstool verwenden.

## Siehe auch

#### Konzepte

[Installieren von optionaler Software in Lync Server 2013](lync-server-2013-installing-optional-software.md)

