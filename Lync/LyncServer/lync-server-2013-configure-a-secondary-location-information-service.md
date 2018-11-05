---
title: Konfigurieren eines sekundären Standortinformationsdiensts in Lync Server 2013
TOCTitle: Konfigurieren eines sekundären Standortinformationsdiensts in Lync Server 2013
ms:assetid: 083ffbc6-7c18-4141-85f9-8825b62c3d10
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg398138(v=OCS.15)
ms:contentKeyID: 49293090
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Konfigurieren eines sekundären Standortinformationsdiensts in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2012-10-30_

Lync Server 2013 stellt eine Webdienstschnittstelle bereit, mit der Sie den Standortinformationsdienst an eine sekundäre Standortdatenbank (Secondary Location Source, SLS) verweisen können. Die mit der Webdienstschnittstelle verbundene SLS-Datenbank muss Standortinformationsdienst-WSDL-konform sein. Wenn sowohl eine Standortdatenbank als auch eine sekundäre Standortdatenbank konfiguriert wurden, fragt der Standortinformationsdienst zunächst die Standortdatenbank ab. Wird kein Treffer ermittelt, wird die Standortanforderung vom Client an die SLS-Datenbank weitergeleitet. Ist der Standort in der SLS-Datenbank enthalten, gibt der Standortinformationsdienst den Standort an den Client zurück.

Ausführliche Informationen finden Sie in der Lync Server-Verwaltungsshell-Dokumentation zu dem folgenden Cmdlet:

  - **Set-CsWebServiceConfiguration**

## So konfigurieren Sie die sekundäre Standortdatenbank (SLS)

1.  Starten der Lync Server-Verwaltungsshell: Klicken Sie auf **Start**, zeigen Sie auf **Alle Programme** und dann auf **Microsoft Lync Server 2013**, und klicken Sie anschließend auf **Lync Server-Verwaltungsshell**.

2.  Führen Sie das folgende Cmdlet aus, um die URL für den Speicherort der SLS-Datenbank zu konfigurieren.
    
        Set-CsWebServiceConfiguration -SecondaryLocationSourceURL "<web service url>"

