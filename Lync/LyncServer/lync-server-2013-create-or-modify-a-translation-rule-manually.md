---
title: 'Lync Server 2013: Manuelles Erstellen oder Ändern einer Übersetzungsregel'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or modify a translation rule manually
ms:assetid: 049d1db3-af58-48c5-be89-52e1d068a4bd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398099(v=OCS.15)
ms:contentKeyID: 48183276
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 372b394619a83ec01ca7a36bac4037c815f09fc1
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41757889"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-translation-rule-manually-in-lync-server-2013"></a>Manuelles Erstellen oder Ändern einer Übersetzungsregel in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-08-06_

Führen Sie die folgenden Schritte aus, wenn Sie eine Übersetzungsregel definieren möchten, indem Sie einen regulären Ausdruck für das Übereinstimmungsmuster und die Übersetzungsregel schreiben. Sie können auch eine Reihe von Werten im Tool zum **Erstellen einer Übersetzungsregel** eingeben und die lync Server-Systemsteuerung aktivieren, um das entsprechende Übereinstimmungsmuster und die entsprechende Übersetzungsregel für Sie zu generieren. Ausführliche Informationen finden Sie unter [erstellen oder Ändern einer Übersetzungsregel mithilfe des Tools zum Erstellen einer Übersetzungsregel in lync Server 2013](lync-server-2013-create-or-modify-a-translation-rule-by-using-the-build-a-translation-rule-tool.md).

<div>

## <a name="to-define-a-translation-rule-manually"></a>So definieren Sie eine Übersetzungsregel manuell

1.  Melden Sie sich auf dem Computer als Mitglied der Gruppe "RTCUniversalServerAdmins" oder als Benutzer mit der Rolle "CsVoiceAdministrator", "CsServerAdministrator" oder "CsAdministrator" an. Ausführliche Informationen finden Sie unter [Delegieren von Setup Berechtigungen in lync Server 2013](lync-server-2013-delegate-setup-permissions.md).

2.  Öffnen Sie ein Browserfenster, und geben Sie dann die Administrator-URL ein, um die lync Server-Systemsteuerung zu öffnen. Details zu den verschiedenen Methoden, die Sie zum Starten der lync Server-Systemsteuerung verwenden können, finden Sie unter [Öffnen von lync Server 2013-Verwaltungstools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Wenn Sie mit dem Definieren einer Übersetzungsregel beginnen möchten, führen Sie die Schritte unter [Konfigurieren eines Trunks mit medienumgehung in lync Server 2013](lync-server-2013-configure-a-trunk-with-media-bypass.md) bis Schritt 10 aus, oder [Konfigurieren Sie einen trunk ohne medienumgehung in lync Server 2013](lync-server-2013-configure-a-trunk-without-media-bypass.md) bis Schritt 9.

4.  Geben Sie im Feld **Name** auf der Seite **Neue Übersetzungsregel** oder **Übersetzungsregel bearbeiten** einen Namen ein, der das zu übersetzende Nummernmuster beschreibt.

5.  (Optional) Geben Sie unter **Beschreibung** eine Beschreibung der Übersetzungsregel ein, z. B. **US International long-distance dialing**.

6.  Klicken Sie im unteren Bereich des Abschnitts **Übersetzungsregel erstellen** auf **Bearbeiten**.

7.  Geben Sie unter **Regulären Ausdruck eingeben** Folgendes ein:
    
      - Geben Sie unter **Übereinstimmung mit dem folgenden Muster** das Muster an, das für den Abgleich der zu übersetzenden Nummern verwendet werden soll.
    
      - Geben Sie unter **Übersetzungsregel** ein Muster für das Format der übersetzten Nummern an.
    
    Wenn Sie beispielsweise ** ^ \\+\\(d{9}\\+) $** in **Übereinstimmung mit diesem Muster** und **011 $1** in der **Übersetzungsregel**eingeben, wird die Regel + 441235551010 in 011441235551010 übersetzen.

8.  Klicken Sie auf **OK**, um die Übersetzungsregel zu speichern.

9.  Klicken Sie auf **OK**, um die Trunkkonfiguration zu speichern.

10. Klicken Sie auf der Seite **Trunkkonfiguration** auf **Commit** und klicken Sie anschließend auf **Commit für alle Elemente ausführen**.
    
    <div>
    

    > [!NOTE]  
    > Immer dann, wenn Sie eine Übersetzungsregel erstellen oder ändern, müssen Sie den Befehl <STRONG>Commit für alle Elemente ausführen</STRONG> ausführen, um die Konfigurationsänderung zu veröffentlichen. Ausführliche Informationen finden Sie unter <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">veröffentlichen ausstehender Änderungen an der VoIP-Routingkonfiguration in lync Server 2013</A> in der Betriebsdokumentation.

    
    </div>

</div>

<div>

## <a name="see-also"></a>Siehe auch


[Erstellen oder Ändern einer Übersetzungsregel mithilfe des Tools zum Erstellen einer Übersetzungsregel in lync Server 2013](lync-server-2013-create-or-modify-a-translation-rule-by-using-the-build-a-translation-rule-tool.md)  
[Configure a trunk with media bypass in Lync Server 2013](lync-server-2013-configure-a-trunk-with-media-bypass.md)  
[Konfigurieren eines Trunks ohne medienumgehung in lync Server 2013](lync-server-2013-configure-a-trunk-without-media-bypass.md)  
[Veröffentlichen ausstehender Änderungen an der VoIP-Routingkonfiguration in lync Server 2013](lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md)  


[Globale Medien Umgehungs Optionen in lync Server 2013](lync-server-2013-global-media-bypass-options.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

