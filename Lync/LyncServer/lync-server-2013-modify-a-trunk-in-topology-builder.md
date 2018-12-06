---
title: Ändern eines Trunks im Topologie-Generator in Lync Server 2013
TOCTitle: Ändern eines Trunks im Topologie-Generator in Lync Server 2013
ms:assetid: 81055a82-c6f8-47b2-9779-223b1d842f36
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ688110(v=OCS.15)
ms:contentKeyID: 49890811
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Ändern eines Trunks im Topologie-Generator in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2012-09-21_

Führen Sie die folgenden Schritte aus, um die alternative IP-Adresse für Medien und die alternative ID für die Umgehung eines Trunk zu ändern.

## So ändern Sie die alternative IP-Adresse für Medien eines Trunks

1.  Starten der Lync Server-Verwaltungsshell: Klicken Sie auf **Start**, zeigen Sie auf **Alle Programme** und dann auf **Microsoft Lync Server 2013**, und klicken Sie anschließend auf **Lync Server-Verwaltungsshell**.

2.  Führen Sie in der Lync Server-Verwaltungsshell das Cmdlet "Set-CsPstnGateway" aus, und ändern Sie das Feld "AlternateBypassId".
    
        Set-CsPstnGateway -Identity "PstnGateway:<peer FQDN> -RepresentativeMediaIP <IP address>

## So ändern Sie die alternative ID für die Umgehung eines Trunks

1.  Starten der Lync Server-Verwaltungsshell: Klicken Sie auf **Start**, zeigen Sie auf **Alle Programme** und dann auf **Microsoft Lync Server 2013**, und klicken Sie anschließend auf **Lync Server-Verwaltungsshell**.

2.  Führen Sie in der Lync Server-Verwaltungsshell das Cmdlet "Set-CsPstnGateway" aus, und ändern Sie das Feld "AlternateBypassId".
    
        Set-CsPstnGateway -Identity "PstnGateway:<peer FQDN> -AlternateBypassID <identifier>

