---
title: 'Lync Server 2013: Manuelles Erstellen oder Ändern einer Normalisierungsregel'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or modify a normalization rule manually
ms:assetid: fc0335e6-8830-4cfb-8c64-6aeb98c0a992
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg413074(v=OCS.15)
ms:contentKeyID: 48185943
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e265563bb7091b72967174a2de11f07d8b8cc29b
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "42151837"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-normalization-rule-manually-in-lync-server-2013"></a>Manuelles Erstellen oder Ändern einer Normalisierungsregel in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-09-22_

Führen Sie die folgenden Schritte aus, wenn Sie eine Normalisierungsregel manuell erstellen oder ändern möchten. Wenn Sie eine Normalisierungsregel mithilfe von Create a normalize Rule in lync Server-Systemsteuerung erstellen oder ändern möchten, finden Sie weitere Informationen unter [erstellen oder Ändern einer Normalisierungsregel mithilfe von Create a normalize Rule in lync Server 2013](lync-server-2013-create-or-modify-a-normalization-rule-by-using-build-a-normalization-rule.md).

<div>

## <a name="to-define-a-normalization-rule-manually"></a>So definieren Sie eine Normalisierungsregel manuell

1.  Melden Sie sich am Computer als Mitglied der RTCUniversalServerAdmins-Gruppe oder als Mitglied der CsVoiceAdministrator-, CsServerAdministrator-oder CsAdministrator-Rolle an. Ausführliche Informationen finden Sie unter [Delegate Setup Permissions in lync Server 2013](lync-server-2013-delegate-setup-permissions.md).

2.  Öffnen Sie ein Browserfenster, und geben Sie die admin-URL ein, um das lync Server-Systemsteuerung zu öffnen. Ausführliche Informationen zu den verschiedenen Methoden, die Sie zum Starten von lync Server-Systemsteuerung verwenden können, finden Sie unter [Open lync Server 2013 Administration Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Optional Führen Sie die Schritte unter [Create a Dial Plan in lync Server 2013](lync-server-2013-create-a-dial-plan.md) oder [Modify a Dial Plan in lync Server 2013](lync-server-2013-modify-a-dial-plan.md)aus.

4.  Geben Sie unter **neue Normalisierungsregel** oder **Normalisierungsregel bearbeiten**einen Namen ein, der das im **Namen** normalisierte Nummernmuster beschreibt (beispielsweise den Namen Normalisierungsregel **5DigitExtension**).

5.  Optional Geben Sie im Feld **Beschreibung** eine Beschreibung der Normalisierungsregel ein (beispielsweise "übersetzt 5-stellige Durchwahlnummern").

6.  Klicken Sie in **Normalisierungsregel erstellen**auf **Bearbeiten**.

7.  Geben Sie in **Regulären Ausdruck eingeben** Folgendes ein:
    
      - Geben Sie unter **dieses Muster abgleichen**das Muster an, das Sie für die Übereinstimmung mit der gewählten Telefonnummer verwenden möchten.
    
      - Geben Sie in **Übersetzungsregel**ein Muster für das Format der übersetzten E. 164-Telefonnummern an.
    
    Wenn Sie beispielsweise **^\\(d{7}) $** in **Übereinstimmung mit diesem Muster** und **+ 1425 $1** in der **Übersetzungsregel**eingeben, normalisiert die Regel 5550100 bis + 14255550100.

8.  Optional Wenn die Normalisierungsregel eine interne Telefonnummer für Ihre Organisation ergibt, wählen Sie **interne Durchwahl**aus.

9.  Optional Geben Sie eine Zahl ein, um die Normalisierungsregel zu testen, und klicken Sie dann auf **go**. Die Testergebnisse werden unterhalb von **Geben Sie eine Testnummer ein** angezeigt.
    
    <div>
    

    > [!NOTE]  
    > Sie können eine Normalisierungsregel speichern, die den Test noch nicht besteht, und Sie dann später neu konfigurieren. Ausführliche Informationen finden Sie unter <A href="lync-server-2013-test-voice-routing.md">Testen der VoIP-Weiterleitung in lync Server 2013</A>.

    
    </div>

10. Klicken Sie auf **OK** , um die Normalisierungsregel zu speichern.

11. Klicken Sie auf **OK** , um die Wähleinstellungen zu speichern.

12. Klicken Sie auf der Seite **Wähleinstellungen** auf **Commit** und anschließend auf **Commit für alle**.
    
    <div>
    

    > [!NOTE]  
    > Wenn Sie eine Normalisierungsregel erstellen oder ändern, müssen Sie den Befehl <STRONG>Commit all</STRONG> ausführen, um die Konfigurationsänderung zu veröffentlichen. Ausführliche Informationen finden Sie unter <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">Veröffentlichen von ausstehenden Änderungen an der VoIP-Routingkonfiguration in lync Server 2013</A> in der Betriebsdokumentation.

    
    </div>

</div>

<div>

## <a name="see-also"></a>Siehe auch


[Erstellen oder Ändern einer Normalisierungsregel mithilfe der Regel zum Erstellen einer Normalisierung in lync Server 2013](lync-server-2013-create-or-modify-a-normalization-rule-by-using-build-a-normalization-rule.md)  
[Erstellen von Wähleinstellungen in lync Server 2013](lync-server-2013-create-a-dial-plan.md)  
[Ändern von Wähleinstellungen in lync Server 2013](lync-server-2013-modify-a-dial-plan.md)  
[Veröffentlichen von ausstehenden Änderungen an der VoIP-Routingkonfiguration in lync Server 2013](lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md)  


[Testen des VoIP-Routings in lync Server 2013](lync-server-2013-test-voice-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

