---
title: 'Lync Server 2013: Aktualisieren der Outlook-Aktivierungs Liste'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Updating the Outlook enable list
ms:assetid: 5db120dc-52f9-4dde-acb9-3824ae245086
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ215438(v=OCS.15)
ms:contentKeyID: 48242739
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 20c7ee75e70b52a4edd01230fe10aeb46f6e6e40
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34847416"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="updating-the-outlook-enable-list-in-lync-server-2013"></a>Aktualisieren der Outlook-Aktivierungs Liste in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2013-01-07_

Sie können sicherstellen, dass das Online Besprechungs-Add-in für Microsoft lync 2013 für Benutzer immer aktiviert bleibt, indem Sie eine Richtlinie erstellen, die Sie in die Add-in-Verwaltungsliste für Outlook einfügt. Die Richtlinie für Add-in-Verwaltungs Listen ist in den Office administrative Template-Dateien für die Gruppenrichtlinien-Verwaltungskonsole enthalten. Sie erstellt einen Registrierungsschlüssel unter HKCU\\-\\Software\\Richtlinien\\Microsoft\\Office\\15,0\\Outlook15 Resilienz\\-Add-in. Sie können diesem Schlüssel einen Wert für die Datei "ucaddin. dll" hinzufügen und den Wert für "ucaddin. dll" so konfigurieren, dass er immer aktiviert ist, sodass Benutzer ihn nicht manuell deaktivieren können.

<div>

## <a name="to-add-ucaddindll-to-the-outlook-add-in-list"></a>So fügen Sie der Outlook-Add-in-Liste ucaddin. dll hinzu

  - Fügen Sie dem Registrierungsschlüssel addinlist\\unter HKCU-Software\\Richtlinien\\,\\Microsoft\\Office\\15,0\\Outlook15-\\Flexibilitäts-Add-in, den folgenden Wert hinzu:
    
      - Registry Type = reg\_SZ
    
      - Name = ucaddin. dll
    
      - Wert = 1 (gibt an, dass das Add-in immer aktiviert ist und nicht vom Endbenutzer verwaltet werden kann)

</div>

</div>

<span> </span>

</div>

</div>

</div>

