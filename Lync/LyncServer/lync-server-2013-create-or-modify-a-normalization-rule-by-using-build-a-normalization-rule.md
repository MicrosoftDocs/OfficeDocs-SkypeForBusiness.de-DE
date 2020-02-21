---
title: Erstellen oder Ändern einer Normalisierungsregel mit Normalisierungsregel erstellen
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or modify a normalization rule by using Build a Normalization Rule
ms:assetid: e8547d7b-f74d-4a73-9a7d-df20d7a87fcd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg399036(v=OCS.15)
ms:contentKeyID: 48185889
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 02bbebae55504fcc27550bae3b90d7fca662a487
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/21/2020
ms.locfileid: "42205477"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-normalization-rule-by-using-build-a-normalization-rule-in-lync-server-2013"></a>Erstellen oder Ändern einer Normalisierungsregel mithilfe der Regel zum Erstellen einer Normalisierung in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-11-01_

Führen Sie die folgenden Schritte aus, wenn Sie eine Normalisierungsregel in lync Server-Systemsteuerung erstellen oder ändern möchten. Wenn Sie eine Normalisierungsregel manuell erstellen oder ändern möchten, finden Sie weitere Informationen unter [erstellen oder Ändern einer Normalisierungsregel manuell in lync Server 2013](lync-server-2013-create-or-modify-a-normalization-rule-manually.md).

<div>

## <a name="to-define-a-rule-by-using-build-a-normalization-rule"></a>So definieren Sie eine Regel mit dem Erstellen einer Normalisierungsregel

1.  Melden Sie sich am Computer als Mitglied der RTCUniversalServerAdmins-Gruppe oder als Mitglied der CsVoiceAdministrator-, CsServerAdministrator-oder CsAdministrator-Rolle an. Ausführliche Informationen finden Sie unter [Delegate Setup Permissions in lync Server 2013](lync-server-2013-delegate-setup-permissions.md).

2.  Öffnen Sie ein Browserfenster, und geben Sie die admin-URL ein, um das lync Server-Systemsteuerung zu öffnen. Ausführliche Informationen zu den verschiedenen Methoden, die Sie zum Starten von lync Server-Systemsteuerung verwenden können, finden Sie unter [Open lync Server 2013 Administration Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Optional Führen Sie die Schritte unter [Erstellen von Wähleinstellungen in lync Server 2013](lync-server-2013-create-a-dial-plan.md) bis Schritt 11 oder [Ändern eines Wählplans in lync Server 2013](lync-server-2013-modify-a-dial-plan.md) bis Schritt 10 aus.

4.  Geben Sie unter **neue Normalisierungsregel** oder **Normalisierungsregel bearbeiten**einen Namen ein, der das im **Namen** normalisierte Nummernmuster beschreibt (beispielsweise **5DigitExtension**).

5.  Optional Geben Sie in **Beschreibung**eine Beschreibung der Normalisierungsregel ein (beispielsweise "übersetzt 5-stellige Durchwahlnummern").

6.  Geben Sie unter **Normalisierungsregel erstellen**Werte in die folgenden Felder ein:
    
      - **Starting digits**   (optional) geben Sie die führenden Ziffern von gewählten Nummern an, die mit dem Muster übereinstimmen sollen. Geben Sie beispielsweise **425** ein, wenn das Muster mit den gewählten Nummern beginnend mit 425 übereinstimmen soll.
    
      - **Length**   geben Sie die Anzahl der Stellen im übereinstimmenden Muster an, und wählen Sie aus, ob das Muster genau mit dieser Länge übereinstimmen soll, mit ausgewählten Nummern, die mindestens diese Länge aufweisen, oder mit den gewählten Nummern einer beliebigen Länge übereinstimmen.
    
      - **Zu entfern**   Ende Ziffern (optional) geben Sie die Anzahl der Start Ziffern an, die aus gewählten Nummern entfernt werden sollen, die mit dem Muster übereinstimmen sollen.
    
      - **Hinzuzufügende**   Ziffern (optional) geben Sie Ziffern an, die gewählten Nummern hinzugefügt werden sollen, die mit dem Muster übereinstimmen sollen.
    
    Die Werte, die Sie in diese Felder eingeben, werden in **Übereinstimmung mit Muster** und **Übersetzungsregel**übernommen. Wenn Sie beispielsweise **Start Ziffern** leer lassen, geben Sie **7** in das Feld **length** ein, und wählen Sie **genau**aus, und geben Sie **0** in **Ziffern zum Entfernen**an, sodass der resultierende reguläre Ausdruck im **Muster mit folgendem übereinstimmt** :
    
    **^ (\\d{7}) $**

7.  Geben Sie in **Übersetzungsregel**ein Muster für das Format der übersetzten E. 164-Telefonnummern wie folgt an:
    
      - Ein Wert, der die Anzahl der im übereinstimmenden Muster angegebenen Ziffern darstellt. Wenn das übereinstimmende Musterbeispiels Weise **^ (\\d{7}) $** ist, dann **$1** in der Übersetzungsregel 7-stellige gewählte Nummern darstellt.
    
      - Optional Geben Sie einen Wert in das Feld **Ziffern hinzufügen** ein, um Ziffern anzugeben, die der übersetzten Zahl vorangestellt werden sollen (beispielsweise **+ 1425**).
    
    Enthält beispielsweise das Muster für die **Übereinstimmung** **^\\({7}d) $** , da das Muster für gewählte Nummern und die **Übersetzungsregel** **+ 1425 $1** als Muster für E. 164-Telefonnummern enthält, normalisiert die Regel 5550100 bis + 14255550100.

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


[Manuelles Erstellen oder Ändern einer Normalisierungsregel in lync Server 2013](lync-server-2013-create-or-modify-a-normalization-rule-manually.md)  
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

