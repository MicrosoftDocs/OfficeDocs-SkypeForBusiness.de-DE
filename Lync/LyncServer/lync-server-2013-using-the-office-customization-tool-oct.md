---
title: Verwenden des Office-Anpassungstools (OAT)
TOCTitle: Verwenden des Office-Anpassungstools (OAT)
ms:assetid: 26647cb6-ba84-4ba7-8b6f-2cf86818e530
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ204748(v=OCS.15)
ms:contentKeyID: 49293468
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Verwenden des Office-Anpassungstools (OAT)

 

_**Letztes Änderungsdatum des Themas:** 2016-12-08_

Das Office-Anpassungstool (OAT) ist Teil des Setupprogramms und stellt das primäre Tool für viele Anpassungen dar. Mithilfe des OAT können Sie Office anpassen. Ihre Anpassungen speichern Sie in einer Setupanpassungsdatei (MSP-Datei). Legen Sie die Datei im Ordner **Updates** im Netzwerkinstallationspfad ab. Bei der Installation von Office sucht das Setupprogramm eine Setupanpassungsdatei im Ordner **Updates** und wendet die Anpassungen an. Der Ordner **Updates** kann nur zur Bereitstellung von Softwarepatches während der Erstinstallation von Office 2013 verwendet werden.

Das OAT ist Teil des Setups und ist in Volumenlizenzversionen des Produkts enthalten. Sie führen das OAT durch Eingeben des Befehls `setup.exe /admin` in die Befehlszeile am Stamm des Netzwerkinstallationspfads aus, der die Quelldateien von Office 2013 enthält. Verwenden Sie beispielsweise folgenden Befehl:

`\\server\share\Office15\setup.exe /admin`

Administratoren verwenden das OAT zum Erstellen einer Setupanpassungsdatei (MSP-Datei). Wie im Microsoft Office 2010 OAT können Administratoren folgende Bereich anpassen:

  - **Setup:** Wird verwendet, um den Standardinstallationsspeicherort auf dem Client und den Standardorganisationsnamen, zusätzliche Netzwerkinstallationsquellen, Product Key, Endbenutzer-Lizenzvertrag, Anzeigeebene, zu entfernende frühere Office-Versionen, während der Installation auszuführende benutzerdefinierte Programme, Sicherheitseinstellungen und Setupeigenschaften anzugeben.

  - **Features:** Wird verwendet, um Benutzereinstellungen zu konfigurieren und um anzupassen, welche Office-Features installiert werden. Administratoren können das OAT verwenden, um anfängliche Standardwerte für die Office-Anwendungseinstellungen der Benutzer festzulegen. Benutzer können die meisten Einstellungen nach der Installation ändern.

  - **Zusätzliche Inhalte:** Wird zum Hinzufügen oder Entfernen von Dateien, zum Hinzufügen oder Entfernen von Registrierungseinträgen und zum Konfigurieren von Verknüpfungen verwendet.

  - **Outlook:** Wird zum Anpassen eines Outlook-Standardprofils des Benutzers, zum Angeben von Exchange-Einstellungen, zum Hinzufügen von Konten, zum Entfernen von Konten, zum Exportieren von Einstellungen und zum Angeben von Senden-Empfangen-Gruppen verwendet.

Informationen zum Office-Anpassungstool (OAT) finden Sie unter [http://go.microsoft.com/fwlink/?linkid=267516\&clcid=0x407](http://go.microsoft.com/fwlink/?linkid=267516%26clcid=0x407).

