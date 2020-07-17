---
title: Migrieren des Adressbuchs
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Migrate Address Book
ms:assetid: b6e000ce-8b2e-460c-8a8b-000254b9d778
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205198(v=OCS.15)
ms:contentKeyID: 48185218
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 937bf9dfff07591ea12a2c78604ab82fa34e97f6
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/16/2020
ms.locfileid: "44757026"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="migrate-address-book"></a>Migrieren des Adressbuchs

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-10-02_

**So migrieren Sie angepasste Normalisierungsregeln für Adressbücher**

1.  Suchen Sie die \_ Normalisierung der Firmentelefonnummer \_ \_ \_Rules.txt Datei im Stammverzeichnis des freigegebenen Adressbuch Ordners, und kopieren Sie Sie in den Stamm des freigegebenen Adressbuch Ordners in Ihrem lync Server 2013-Pilot Pool.
    
    <div>
    

    > [!NOTE]  
    > Die Beispiele für die Normalisierungsregeln für Adressbücher wurden in Ihrem ABS Web-Komponentendateiverzeichnis installiert. Der Pfad lautet <STRONG>$installedDriveLetter:\Program Files\Microsoft Lync Server 2013\Web Components\Address Book Files\Files\ Sample_Company_Phone_Number_Normalization_Rules.txt,</STRONG>. Diese Datei kann kopiert und als &nbsp; <STRONG>Company_Phone_Number_Normalization_Rules.txt</STRONG> &nbsp; in das Stammverzeichnis des freigegebenen Adressbuch Ordners umbenannt werden. Beispielsweise ist das in <STRONG>$serverX</STRONG>freigegebene Adressbuch &nbsp; der Pfad ähnlich wie: <STRONG> \\ $serverX \LyncFileShare\2-Webservices-1\ABFiles</STRONG>.

    
    </div>

2.  Verwenden Sie einen Text-Editor wie Editor, um die \_ \_ \_ Normalisierung \_Rules.txt Datei für Firmennummern zu öffnen.

3.  Bestimmte Typen von Einträgen funktionieren in lync Server 2013 nicht ordnungsgemäß. Durchsuchen Sie die Datei nach den hier beschriebenen Typen von Einträgen, bearbeiten Sie die Einträge entsprechend, und speichern Sie die Änderungen im freigegebenen Adressbuchordner im Pilotpool.
    
    Zeichenfolgen, die erforderliche Leerzeichen oder Satzzeichen enthalten, können Fehler bei der Ausführung der Normalisierungsregeln verursachen, weil diese Zeichen aus den Zeichenfolgen, die in die Normalisierungsregeln eingelesen werden, entfernt werden. Wenn Sie Zeichenfolgen mit erforderlichen Leerzeichen oder Satzzeichen haben, müssen Sie diese Zeichenfolgen bearbeiten. Beispielsweise würde die folgende Zeichenfolge einen Fehler bei der Normalisierungsregel verursachen:
    
        \s*\(\s*\d\d\d\s*\)\s*\-\s*\d\d\d\s*\-\s*\d\d\d\d
    
    Mit der folgenden Zeichenfolge würde die Normalisierungsregel fehlerfrei ausgeführt werden:
    
        \s*\(?\s*\d\d\d\s*\)?\s*\-?\s*\d\d\d\s*\-?\s*\d\d\d\d

</div>

<span> </span>

</div>

</div>

</div>

