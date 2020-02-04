---
title: 'Lync Server 2013: Verwenden des Office-Anpassungstools (OAT)'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Using the Office Customization Tool (OCT)
ms:assetid: 26647cb6-ba84-4ba7-8b6f-2cf86818e530
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204748(v=OCS.15)
ms:contentKeyID: 48183654
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b82db655a0b55858de9cdc32efd1a3f110247b54
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41743845"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="using-the-office-customization-tool-oct-in-lync-server-2013"></a>Verwenden des Office-Anpassungstools (OAT) in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-10-02_

Das Office-Anpassungstool (OAT) ist Teil des Setup-Programms und wird als Tool für viele Anpassungen empfohlen. Wenn Sie das OAT verwenden, passen Sie Office an, und speichern Sie Ihre Anpassungen in einer MSP-Datei für die Setup Anpassung. Sie fügen die Datei im Ordner Updates auf dem Netzwerkinstallationspfad ein. Wenn Sie Office installieren, sucht Setup im Ordner Updates nach einer Setupanpassungsdatei und wendet die Anpassungen an. Der Ordner Updates kann nur zum Bereitstellen von Softwareupdates während einer Erstinstallation von Office 2013 verwendet werden.

Das OAT ist Teil des Setups und in Volumenlizenzversionen des Produkts enthalten. Sie führen das OAT durch Eingabe `setup.exe /admin` über die Befehlszeile aus dem Stammverzeichnis des Netzwerkinstallationspfads, der die Office 2013-Quelldateien enthält. Verwenden Sie beispielsweise folgenden Befehl:

`\\server\share\Office15\setup.exe /admin`

Administratoren verwenden das OAT zum Erstellen einer Setupanpassungsdatei (MSP-Datei). Wie im Microsoft Office 2010 Oct können Administratoren die folgenden Bereiche anpassen:

  - **Einrichtung** Dient zum Angeben des Standard Installationsspeicherorts auf dem Client und dem Standard Organisationsnamen, zusätzliche Netzwerkinstallationsquellen, Product Key, Endbenutzer-Lizenzvertrag, Anzeigeebene, zu entfernende frühere Versionen von Office, benutzerdefinierte Programme, die während der Installation, Sicherheitseinstellungen und Setup Eigenschaften ausgeführt werden sollen.

  - **Funktionen** Wird verwendet, um Benutzereinstellungen zu konfigurieren und die Installation von Office-Features anzupassen. Administratoren können das OAT verwenden, um anfängliche Standardwerte für die Office-Anwendungseinstellungen für Benutzer festzulegen. Benutzer können die meisten Einstellungen nach der Installation ändern.

  - **Zusätzlicher Inhalt** Wird zum Hinzufügen oder Entfernen von Dateien, hinzufügen oder Entfernen von Registrierungseinträgen und Konfigurieren von Tastenkombinationen verwendet.

  - **Outlook** Wird verwendet, um das standardmäßige Outlook-Profil eines Benutzers anzupassen, Exchange-Einstellungen anzugeben, Konten hinzuzufügen, Konten zu\\entfernen und Einstellungen zu exportieren sowie Senden von Empfangs Gruppen anzugeben.

Informationen zum OAT finden Sie unter <http://go.microsoft.com/fwlink/p/?linkid=267516>.

</div>

<span> </span>

</div>

</div>

</div>

