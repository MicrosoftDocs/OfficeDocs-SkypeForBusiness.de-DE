---
title: 'Lync Server 2013: Aktualisieren der Outlook-Aktivierungs Liste'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Updating the Outlook enable list
ms:assetid: 5db120dc-52f9-4dde-acb9-3824ae245086
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ215438(v=OCS.15)
ms:contentKeyID: 48242739
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1e1f71d1ef0ebcb6bc5f8aee8875c013a24a4de0
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "42140898"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="updating-the-outlook-enable-list-in-lync-server-2013"></a>Aktualisieren der Outlook-Aktivierungs Liste in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2013-01-07_

Sie können sicherstellen, dass das Online Besprechungs-Add-in für Microsoft lync 2013 für Benutzer immer aktiviert bleibt, indem Sie eine Richtlinie erstellen, die Sie in der Add-in-Verwaltungsliste für Outlook einschließt. Die Add-in-Verwaltungs Listen Richtlinie ist in den Office administrative Template-Dateien für die Gruppenrichtlinien-Verwaltungskonsole enthalten. Es erstellt einen Registrierungsschlüssel unter HKCU\\-\\Software\\Richtlinien\\Microsoft\\Office\\15,0\\Outlook15 Resilienz\\-Add-in. Sie können diesem Schlüssel einen Wert für die ucaddin. dll hinzufügen und den Wert von ucaddin. dll so konfigurieren, dass er immer aktiviert ist und die Benutzer ihn nicht manuell deaktivieren können.

<div>

## <a name="to-add-ucaddindll-to-the-outlook-add-in-list"></a>So fügen Sie der Outlook-Add-in-Liste ucaddin. dll hinzu

  - Fügen Sie den folgenden Wert zum Add-in-\\Registrierungs\\Schlüssel\\hinzu\\,\\der\\sich\\unter HKCU\\-Software Richtlinien Microsoft Office 15,0 Outlook15-Ausfall-Add-in befindet:
    
      - Registrierungstyp = reg\_SZ
    
      - Name = ucaddin.dll
    
      - Value = 1 (gibt an, dass das Add-In immer aktiviert ist und vom Benutzer nicht deaktiviert werden kann)

</div>

</div>

<span> </span>

</div>

</div>

</div>

