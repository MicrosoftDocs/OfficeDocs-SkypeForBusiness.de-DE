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
ms.openlocfilehash: b2203c4169075b7b906156bf3436e61011f873a4
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/14/2020
ms.locfileid: "42007474"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="using-the-office-customization-tool-oct-in-lync-server-2013"></a>Verwenden des Office-Anpassungstools (OAT) in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-10-02_

Das Office-Anpassungstool (OAT) ist Teil des Setup-Programms und ist das empfohlene Tool für viele Anpassungen. Mithilfe des OAT passen Sie Office an und speichern Ihre Anpassungen in einer MSP-Setup Anpassungsdatei. Legen Sie die Datei am Netzwerkinstallationspfad im Ordner "Updates" ab. Bei der Installation von Office sucht das Setupprogramm nach einer Setupanpassungsdatei im Ordner Updates und wendet die Anpassungen an. Der Ordner Updates kann nur zum Bereitstellen von Softwareupdates während einer Erstinstallation von Office 2013 verwendet werden.

Das OAT ist Teil des Setups und ist in Volumenlizenzversionen des Produkts enthalten. Sie führen das OAT aus, `setup.exe /admin` indem Sie an der Befehlszeile im Stammverzeichnis des Netzwerkinstallationspfads, der die Office 2013 Quelldateien enthält, eingeben. Verwenden Sie beispielsweise folgenden Befehl:

`\\server\share\Office15\setup.exe /admin`

Administratoren verwenden das OAT zum Erstellen einer Setupanpassungsdatei (MSP-Datei). Wie im Microsoft Office 2010 OAT können Administratoren die folgenden Bereiche anpassen:

  - **Setup** Wird verwendet, um den Standard Installationsspeicherort auf dem Client und den Standard Organisationsnamen, zusätzliche Netzwerkinstallationsquellen, Product Key, Endbenutzer-Lizenzvertrag, Anzeigeebene, zu entfernende frühere Office-Versionen, benutzerdefinierte Programme zur Ausführung während der Installation, Sicherheitseinstellungen und Setup Eigenschaften anzugeben.

  - **Funktionen** Dient zum Konfigurieren von Benutzereinstellungen und zum Anpassen der Installation von Office-Features. Administratoren können das OAT verwenden, um anfängliche Standardwerte für Office-Anwendungseinstellungen für Benutzer anzugeben. Benutzer können die meisten Einstellungen nach der Installation ändern.

  - **Zusätzlicher Inhalt** Wird zum Hinzufügen oder Entfernen von Dateien, zum Hinzufügen oder Entfernen von Registrierungseinträgen und zum Konfigurieren von Verknüpfungen verwendet.

  - **Outlook** Dient zum Anpassen des Outlook-Standardprofils eines Benutzers, zum Angeben von Exchange-Einstellungen, zum Hinzufügen von Konten, zum Entfernen\\von Konten und zum Exportieren von Einstellungen und zum Angeben von Sende Empfangs Gruppen.

Weitere Informationen zum OAT finden Sie unter <http://go.microsoft.com/fwlink/p/?linkid=267516>.

</div>

<span> </span>

</div>

</div>

</div>

