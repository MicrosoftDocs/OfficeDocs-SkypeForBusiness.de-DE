---
title: Ändern der VoIP-Routen für die Verwendung der neuen lync Server 2013 Vermittlungsserver
description: Ändern Sie VoIP-Routen, um die neue lync Server 2013 Vermittlungsserver zu verwenden.
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
audience: Admin
f1.keywords:
- NOCSH
TOCTitle: Change voice routes to use the new Lync Server 2013 Mediation Server
ms:assetid: acd487b3-377c-46bf-9f71-fe6152002664
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205162(v=OCS.15)
ms:contentKeyID: 48185069
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ef58ba61512b5de31a74b79e554dbb3f94b67d99
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48545741"
---
# <a name="change-voice-routes-to-use-the-new-lync-server-2013-mediation-server"></a>Ändern der VoIP-Routen für die Verwendung der neuen lync Server 2013 Vermittlungsserver

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-09-28_

Bei diesem Verfahren werden die VoIP-Routen so geändert, dass die lync Server 2013 Vermittlungsserver anstelle der Legacy Office Communications Server 2007 R2 Vermittlungsserver verwendet werden.

<div>

## <a name="to-change-the-voice-routes-to-use-the-new-mediation-server"></a>So ändern Sie die VoIP-Routen für die Verwendung des neuen Vermittlungsservers

1.  Lync Server 2013-Systemsteuerung

2.  Wählen Sie im linken Bereich **VoIP-Routing** und dann **Route** aus.

3.  Klicken Sie auf **Neu**, um eine neue VoIP-Route zu erstellen.

4.  Füllen Sie die folgenden Felder aus:
    
      - **Name**: Geben Sie einen beschreibenden Namen für die VoIP-Route ein. Im Rahmen dieses Dokuments wird **W15PSTNRoute** verwendet.
    
      - **Beschreibung**: Geben Sie eine kurze Beschreibung für die VoIP-Route ein.

5.  Überspringen Sie alle verbleibenden Abschnitte, bis Sie zu **Zugeordnete Gateways** gelangen. Klicken Sie auf **Hinzufügen**. Wählen Sie das neue Standardgateway aus, und klicken Sie auf **OK**.

6.  Klicken Sie unter **Zugeordnete PSTN-Verwendungen** auf **Auswählen**.

7.  Wählen Sie auf der Seite **PSTN-Verwendungseintrag auswählen** den Namen eines Eintrags aus, klicken Sie dann auf **OK**.

8.  Klicken Sie auf der Seite **Neue VoIP-Route** auf **OK**, um die **VoIP-Route** zu erstellen.

9.  Wählen Sie auf der Seite **VoIP-Routing** die Option **Route** aus.

10. Verschieben Sie die neu erstellte Route an den Anfang der Liste, und wählen Sie dann **Commit** aus.

</div>

</div>

<span> </span>

</div>

</div>

</div>

