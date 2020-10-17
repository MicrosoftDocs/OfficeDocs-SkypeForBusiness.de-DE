---
title: 'Lync Server 2013: Überprüfen der Schemareplikation'
description: 'Lync Server 2013: Überprüfen der Schemareplikation.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Verifying schema replication
ms:assetid: ad01a7cf-aa79-4648-ba5a-a7a09172db36
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412822(v=OCS.15)
ms:contentKeyID: 48185124
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 019cd06db05a9ba683767f550a712ef188b47508
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48560171"
---
# <a name="verifying-active-directory-schema-replication-in-lync-server-2013"></a>Überprüfen Active Directory Schemareplikation in lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-10-29_

Überprüfen Sie vor dem Ausführen der Gesamtstrukturvorbereitung manuell, ob die Schemapartition repliziert wurde.

<div>

## <a name="to-manually-verify-schema-replication"></a>So überprüfen Sie die Schemareplikation manuell

1.  Melden Sie sich bei einem Domänencontroller als Mitglied der Gruppe "Organisations-Admins" an.

2.  Öffnen Sie den ADSI-Editor, indem Sie nacheinander auf **Start**, **Verwaltung** und dann auf **ADSI-Editor** klicken.
    
    <div>
    

    > [!TIP]  
    > Alternativ dazu können Sie <STRONG>adsiedit.msc</STRONG> auch über die Befehlszeile ausführen.

    
    </div>

3.  Klicken Sie in der MMC-Konsolenstruktur (Microsoft Management Console) auf **ADSI-Editor**, falls er nicht bereits ausgewählt ist.

4.  Klicken Sie im Menü **Aktion** auf **Verbinden mit**.

5.  Wählen Sie im Dialogfeld **Verbindungseinstellungen** unter **Bekannten Namenskontext auswählen** die Option **Schema** aus, und klicken Sie auf **OK**.

6.  Suchen Sie unter dem Schemacontainer nach "CN=ms-RTC-SIP-SchemaVersion". Wenn dieses Objekt vorhanden und der Wert des Attributs **rangeUpper** 1150 und der Wert des Attributs **rangeLower** 3 ist, wurde das Schema erfolgreich aktualisiert und repliziert. Wenn dieses Objekt nicht vorhanden ist oder die Werte der Attribute **rangeUpper** und **rangeLower** nicht diesen Werten entsprechen, wurde das Schema nicht geändert oder repliziert.

</div>

<div>

## <a name="see-also"></a>Siehe auch


[Durchführen Active Directory Schemavorbereitung in lync Server 2013](lync-server-2013-running-schema-preparation.md)  


[Vorbereiten des Active Directory Schemas in lync Server 2013](lync-server-2013-preparing-the-active-directory-schema.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

