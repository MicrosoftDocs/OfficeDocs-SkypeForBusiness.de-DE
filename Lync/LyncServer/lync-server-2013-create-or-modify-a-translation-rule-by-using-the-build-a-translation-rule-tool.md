---
title: Erstellen oder Ändern einer Übersetzungsregel mithilfe des Tools zum Erstellen einer Übersetzungsregel
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or modify a translation rule by using the Build a Translation Rule tool
ms:assetid: ba112df8-3bb4-48e4-a353-4bf9110ccd71
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412909(v=OCS.15)
ms:contentKeyID: 48185224
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8321603c699fb0f25fc0a3a1b94e8b216761c6b4
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/14/2020
ms.locfileid: "42006341"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-translation-rule-by-using-the-build-a-translation-rule-tool-in-lync-server-2013"></a>Erstellen oder Ändern einer Übersetzungsregel mithilfe des Tools zum Erstellen einer Übersetzungsregel in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-10-05_

Führen Sie die folgenden Schritte aus, wenn Sie eine Übersetzungsregel definieren möchten, indem Sie einen Wertesatz in das Tool zum **Erstellen einer Übersetzungsregel** eingeben und lync Server-Systemsteuerung das entsprechende Übereinstimmungsmuster und die Übersetzungsregel für Sie generieren. Alternativ können Sie einen regulären Ausdruck manuell schreiben, um das übereinstimmende Muster und die Übersetzungsregel zu definieren. Ausführliche Informationen finden Sie unter [erstellen oder Ändern einer Übersetzungsregel manuell in lync Server 2013](lync-server-2013-create-or-modify-a-translation-rule-manually.md).

<div>

## <a name="to-define-a-rule-by-using-the-build-a-translation-rule-tool"></a>So definieren Sie eine Regel mit dem Tool zum Erstellen einer Übersetzungsregel

1.  Melden Sie sich am Computer als Mitglied der RTCUniversalServerAdmins-Gruppe oder als Mitglied der CsVoiceAdministrator-, CsServerAdministrator-oder CsAdministrator-Rolle an. Ausführliche Informationen finden Sie unter [Delegate Setup Permissions in lync Server 2013](lync-server-2013-delegate-setup-permissions.md).

2.  Öffnen Sie ein Browserfenster, und geben Sie die admin-URL ein, um das lync Server-Systemsteuerung zu öffnen. Ausführliche Informationen zu den verschiedenen Methoden, die Sie zum Starten von lync Server-Systemsteuerung verwenden können, finden Sie unter [Open lync Server 2013 Administration Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Um mit der Definition einer Übersetzungsregel zu beginnen, führen Sie die Schritte unter [Configure a trunk with Media Bypass in lync Server 2013](lync-server-2013-configure-a-trunk-with-media-bypass.md) through Step 10 durch, oder [Konfigurieren Sie einen trunk ohne medienumgehung in lync Server 2013](lync-server-2013-configure-a-trunk-without-media-bypass.md) bis Schritt 9.

4.  Geben Sie unter **Name** auf der Seite **neue Übersetzungsregel** oder **Übersetzungsregel bearbeiten** einen Namen ein, der das zu übersetzende Nummernmuster beschreibt.

5.  Optional Geben Sie unter **Beschreibung**eine Beschreibung der Übersetzungsregel ein, beispielsweise **US International Dialing**(Ferngespräche).

6.  Geben Sie im Abschnitt **Übersetzungsregel erstellen** des Dialogfelds Werte in die folgenden Felder ein:
    
      - **Starting digits**: (optional) geben Sie die führenden Ziffern von Zahlen an, die mit dem Muster übereinstimmen sollen. Geben Sie **+** beispielsweise in dieses Feldnummern im E. 164-Format (die mit + beginnen) überein.
    
      - **Length**: Geben Sie die Anzahl der Stellen im übereinstimmenden Muster an, und wählen Sie aus, ob das Muster Zahlen entsprechen soll, die diese Länge genau, mindestens diese Länge oder eine beliebige Länge aufweisen. Geben Sie beispielsweise **11** ein, und wählen Sie **mindestens** in der Dropdownliste aus, um Nummern mit einer Länge von mindestens 11 Ziffern abzugleichen.
    
      - **Zu entfernende Ziffern**: (optional) geben Sie die Anzahl der zu entfernenden Start Ziffern an. Geben Sie beispielsweise **1** ein, um den **+** vom Anfang der Zahl zu entfernen.
    
      - **Hinzuzufügende Ziffern**: (optional) geben Sie Ziffern an, die den übersetzten Zahlen vorangestellt werden sollen. Geben Sie beispielsweise " **011** " ein, wenn Sie möchten, dass die übersetzten Nummern beim Anwenden der Regel auf "011" vorangestellt werden.
    
    Die in diesen Feldern eingegebenen Werte werden in den Feldern **Muster für Übereinstimmung** und **Übersetzungsregel** wiedergegeben. Wenn Sie beispielsweise die obigen Beispielwerte angeben, lautet der resultierende reguläre Ausdruck im Feld **Muster an Übereinstimmung** wie folgt:
    
    **^\\+ (\\d{9}\\d +) $**
    
    Das Feld **Übersetzungsregel** gibt ein Muster für das Format der übersetzten Zahlen an. Dieses Muster besteht aus zwei Teilen:
    
      - Ein Wert (beispielsweise **$1**), der die Anzahl der Stellen im übereinstimmenden Muster darstellt.
    
      - Optional Ein Wert, den Sie voranstellen können, indem Sie ihn in das Feld **hinzuzufügende Ziffern** eingeben
    
    Mit den obigen Beispielwerten wird **011 $1** im **Übersetzungsregel** Feld angezeigt.
    
    Wenn diese Übersetzungsregel angewendet wird, wird + 441235551010 zu 011441235551010.

7.  Klicken Sie auf **OK**, um die Übersetzungsregel zu speichern.

8.  Klicken Sie auf **OK**, um die Trunkkonfiguration zu speichern.

9.  Klicken Sie auf der Seite **Trunkkonfiguration** auf **Commit**, und klicken Sie anschließend auf **Commit für alle**.
    
    <div>
    

    > [!NOTE]
    > Jedes Mal, wenn Sie eine Übersetzungsregel erstellen oder ändern, müssen Sie den Befehl <STRONG>Commit für alle Elemente ausführen</STRONG> ausführen, um die Konfigurationsänderung zu veröffentlichen. Ausführliche Informationen finden Sie unter <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">Veröffentlichen von ausstehenden Änderungen an der VoIP-Routingkonfiguration in lync Server 2013</A> in der Betriebsdokumentation.

    
    </div>

</div>

<div>

## <a name="see-also"></a>Siehe auch


[Manuelles Erstellen oder Ändern einer Übersetzungsregel in lync Server 2013](lync-server-2013-create-or-modify-a-translation-rule-manually.md)  
[Konfigurieren eines Trunks mit medienumgehung in lync Server 2013](lync-server-2013-configure-a-trunk-with-media-bypass.md)  
[Konfigurieren eines Trunks ohne medienumgehung in lync Server 2013](lync-server-2013-configure-a-trunk-without-media-bypass.md)  
[Veröffentlichen von ausstehenden Änderungen an der VoIP-Routingkonfiguration in lync Server 2013](lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md)  


[Optionen für die globale medienumgehung in lync Server 2013](lync-server-2013-global-media-bypass-options.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

