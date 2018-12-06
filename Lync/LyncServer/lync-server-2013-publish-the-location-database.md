---
title: Veröffentlichen der Standortdatenbank von Lync Server 2013
TOCTitle: Veröffentlichen der Standortdatenbank von Lync Server 2013
ms:assetid: dd032b5b-df0e-4017-ac46-e17570c1ab1e
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg398974(v=OCS.15)
ms:contentKeyID: 49295628
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Veröffentlichen der Standortdatenbank von Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2012-10-30_

Die neuen Standorte, die Sie der Standortdatenbank hinzugefügt haben, stehen dem Client erst nach der Veröffentlichung zur Verfügung.

Ausführliche Informationen finden Sie in der Lync Server-Verwaltungsshell-Dokumentation zu dem folgenden Cmdlet:

  - **Publish-CsLisConfiguration**

Wenn Sie ELIN-Gateways (Emergency Location Identification Number) verwenden, müssen Sie auch die die ELINs in die ALI (Automatic Location Identification)-Datenbank Ihres PSTN-Betreibers hochladen. Ihr PSTN-Betreiber verlangt möglicherweise, dass Sie ein bestimmtes Format für die ELIN-Einträge verwenden. Weitere Informationen erhalten Sie von Ihrem PSTN-Betreiber. Die Einträge können Sie aus der Standortinformationsdienst-Datenbank exportieren und entsprechend formatieren.

## So veröffentlichen Sie die Standortdatenbank

  - Starten der Lync Server-Verwaltungsshell: Klicken Sie auf **Start**, zeigen Sie auf **Alle Programme** und dann auf **Microsoft Lync Server 2013**, und klicken Sie anschließend auf **Lync Server-Verwaltungsshell**.

  - Führen Sie das folgende Cmdlet aus, um die Standortdatenbank zu veröffentlichen.
    
        Publish-CsLisConfiguration

