---
title: 'Lync Server 2013: Überprüfen der Schemareplikation'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Verifying schema replication
ms:assetid: ad01a7cf-aa79-4648-ba5a-a7a09172db36
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412822(v=OCS.15)
ms:contentKeyID: 48185124
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d115738a4f22cb7795c2eb5a00ac642fbe43fc77
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34847280"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="verifying-active-directory-schema-replication-in-lync-server-2013"></a>Überprüfen der Active Directory-Schemareplikation in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-10-29_

Bevor Sie die Gesamtstrukturvorbereitung ausführen, überprüfen Sie manuell, ob die Schemapartition repliziert wurde.

<div>

## <a name="to-manually-verify-schema-replication"></a>So überprüfen Sie die Schemareplikation manuell

1.  Melden Sie sich bei einem Domänencontroller als Mitglied der Gruppe "Unternehmensadministratoren" an.

2.  Öffnen Sie die ADSI-Bearbeitung, indem Sie auf **Start**, dann auf **Verwaltung**und dann auf **ADSI-Bearbeitung**klicken.
    
    <div>
    

    > [!TIP]  
    > Alternativ können Sie <STRONG>Adsiedit. msc</STRONG> über die Befehlszeile ausführen.

    
    </div>

3.  Klicken Sie in der MMC-Struktur (Microsoft Management Console) auf **ADSI-Bearbeitung**, wenn Sie noch nicht ausgewählt ist.

4.  Klicken Sie im Menü **Aktion** auf **Verbinden mit**.

5.  Wählen Sie im Dialogfeld **Verbindungseinstellungen** unter **Bekannten Namenskontext auswählen** die Option **Schema** aus und klicken Sie dann auf **OK**.

6.  Suchen Sie unter dem Schemacontainer nach CN=ms-RTC-SIP-SchemaVersion. Wenn dieses Objekt vorhanden ist und der Wert des **rangeUpper** -Attributs 1150 ist und der Wert des **rangeLower** -Attributs 3 ist, wurde das Schema erfolgreich aktualisiert und repliziert. Wenn dieses Objekt nicht vorhanden ist oder die Werte der **rangeUpper** -und **rangeLower** -Attribute nicht wie angegeben sind, wurde das Schema nicht geändert oder nicht repliziert.

</div>

<div>

## <a name="see-also"></a>Siehe auch


[Ausführen der Active Directory-Schemavorbereitung in Lync Server 2013](lync-server-2013-running-schema-preparation.md)  


[Vorbereiten des Active Directory-Schemas in Lync Server 2013](lync-server-2013-preparing-the-active-directory-schema.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

