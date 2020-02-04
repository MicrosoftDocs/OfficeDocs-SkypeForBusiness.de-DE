---
title: Entfernen der Zuordnung des Archivierungsservers
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Remove the Archiving server association
ms:assetid: dabac157-71ee-4afe-b0b6-4a083d165ffb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721903(v=OCS.15)
ms:contentKeyID: 49733837
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 04bf1a5a3c68ab1123431543e08618c4eacb7559
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41727115"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="remove-the-archiving-server-association"></a>Entfernen der Zuordnung des Archivierungsservers

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-10-04_

Um einen Archivierungsserver zu entfernen, müssen Sie die Abhängigkeit auf dem zugehörigen Front-End-Pool, dem Front-End-Server, der Survivable Branch-Appliance und dem Überlebenden Branch-Server ändern oder deaktivieren. Sie bearbeiten die Eigenschaften des Front-End-Pools, des Front-End-Servers, der Survivable-Branch-Appliance und des Survivable Branch-Servers, um die Abhängigkeit zu entfernen. Nachdem Sie die Abhängigkeit gelöscht und den Server im Topologie-Generator gelöscht haben, werden Sie benachrichtigt, dass das zugeordnete Datenbankspeicher Objekt im Topologie-Generator ebenfalls gelöscht wird.

<div>

## <a name="to-remove-the-archiving-server-association"></a>So entfernen Sie die Zuordnung des Archivierungsservers

1.  Öffnen Sie den lync Server 2013-Front-End-Server, öffnen Sie den Topologie-Generator.

2.  Navigieren Sie zum lync Server 2010-Knoten.

3.  Erweitern Sie im Topologie-Generator **Enterprise Edition-Front-End-Pools**, **Standard Edition-Front-End-Server**oder **Zweigstellen**, basierend auf der Definition des Archivierungsservers.

4.  Wenn Sie über einen Überlebenden Branch Server verfügen, erweitern Sie **Zweigstellen**, erweitern Sie den Namen der Verzweigungs Website, und erweitern Sie dann **Survivable Branch Appliances**.
    
    <div>
    

    > [!NOTE]  
    > <STRONG>Survivable-Branch-Appliances</STRONG> auf der Benutzeroberfläche gelten sowohl für Survival Branch-Server als auch für Survivable Branch-Appliance.

    
    </div>

5.  Klicken Sie mit der rechten Maustaste auf den Pool, den Server oder das Gerät, der dem Archivierungsserver zugeordnet ist, und klicken Sie dann auf **Eigenschaften bearbeiten**.

6.  Deaktivieren Sie in **Eigenschaften bearbeiten**unter **Allgemein**unter **Zuordnungen**das Kontrollkästchen **Archivierungs Server zuordnen** , und klicken Sie dann auf **OK**.

7.  Wiederholen Sie den vorherigen Schritt für alle anderen Pools, Server oder Geräte, die dem Archivierungsserver zugeordnet sind, den Sie entfernen möchten.

8.  Klicken Sie mit der rechten Maustaste auf den Archivierungs Server, und klicken Sie dann auf **Löschen**.

9.  Klicken Sie unter **abhängige Speicher löschen**auf **OK**.

10. Veröffentlichen Sie die Topologie, überprüfen Sie den Replikationsstatus, und führen Sie dann den lync Server-Bereitstellungs-Assistenten nach Bedarf aus.

</div>

</div>

<span> </span>

</div>

</div>

</div>

