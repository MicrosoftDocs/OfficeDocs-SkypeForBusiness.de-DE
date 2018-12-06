---
title: Konfigurieren der Videobandbreite in Lync Server 2013
TOCTitle: Konfigurieren der Videobandbreite in Lync Server 2013
ms:assetid: 446bed91-b26f-4ab2-b2f5-36e6810b405b
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ204842(v=OCS.15)
ms:contentKeyID: 49293847
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Konfigurieren der Videobandbreite in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2012-10-02_

Lync Server 2013 beinhaltet verschiedene Einstellungen zum Verwalten von Videos für Anrufe mit zwei und Konferenzen mit mehreren Teilnehmern. Bei der Bereitstellung von Lync Server 2013 sollten Sie überprüfen, ob die Standardeinstellungen für Ihre Organisation geeignet sind und sie gegebenenfalls anpassen.

Die in diesem Abschnitt beschriebenen Parameter gelten für Anrufe mit zwei und Konferenzen mit mehreren Teilnehmern. Sie können diese Einstellungen mithilfe eines der folgenden Cmdlets anzeigen oder ändern:

  - **Get-CsConferencingPolicy**

  - **Set-CsConferencingPolicy**

  - **New-CsConferencingPolicy**

Überprüfen Sie in Ihrer Konferenzrichtlinie die folgenden Einstellungen:

  - **VideoBitRateKb**   Diese Einstellung gibt die maximale Videobitrate in Kilobit pro Sekunde (kb/s) an, die für von einem Benutzer gesendete Videos verwendet wird. Der Standardwert ist 50.000 KBit/s. Gültige Werte sind 0 bis 50.000 KBit/s.
    
    Diese Einstellung gilt separat für Haupt- und Panoramavideo.
    
    Beispiel: Wenn Sie 2.000 KBit/s angeben, kann Lync Server jeweils 2.000 KBit/s für den Haupt- und 2.000 KBit/s für den Panoramavideo-Stream senden.
    

    > [!NOTE]
    > Die maximale Video-Netzwerkbandbreite für einen Lync 2013-Endpunkt beträgt 8.000&nbsp;KBit/s für das Haupt- und 2.500&nbsp;KBit/s für das Panoramavideo. Diese Höchstwerte werden nur erreicht, wenn mehrere Videos gesendet oder empfangen werden. Ausführliche Informationen finden Sie im Abschnitt "Netzwerkbelegung durch Mediendatenverkehr" in <A href="lync-server-2013-network-bandwidth-requirements-for-media-traffic.md">Anforderungen hinsichtlich der Netzwerkbandbreite für Mediendatenverkehr</A>. In diesem Abschnitt sind die maximale und typische Videostream-Bandbreite für alle unterstützen Auflösungen aufgeführt.



  - **TotalReceiveVideoBitRateKb**   Diese Einstellung, die in Lync Server 2013 neu eingeführt wurde, gibt die maximale zulässige Bitrate (in Kilobit pro Sekunde) für alle Videostreams an, die von einem Client empfangen werden kann. Dies bedeutet, dass damit der kombinierte Gesamtwert für alle Videostreams mit Ausnahme der Panoramavideo-Streams angegeben wird, die ein Client empfangen kann. Wenn Sie beispielsweise 1.500 KBit/s angeben, kann ein Client bis zu 1.500 KBit/s an Videoinhalten empfangen, die aus einem einzelnen oder mehreren Videostreams bestehen können. Diese Einstellung gilt nur für Lync Server 2013-Clients.
    
    Der Standardwert für **TotalReceiveVideoBitRateKb** ist 50.000 KBit/s. Wenn die **EnableMultiviewJoin**-Einstellung für die Katalogansicht auf "True" festgelegt ist, darf **TotalReceiveVideoBitRateKb** nicht auf weniger als 420 KBit/s festgelegt sein. Wenn die **EnableMultiviewJoin**-Einstellung für die Katalogansicht auf "True" festgelegt ist, darf **TotalReceiveVideoBitRateKb** nicht auf weniger als 100 KBit/s festgelegt sein. Wenn **EnableMultiviewJoin** auf "True" festgelegt ist und Sie den Wert auf weniger als 420 KBit/s festlegen, werden die Werte standardmäßig auf den Schwellenwert festgelegt. Dieser Schwellenwert verhindert versehentliche Fehlkonfigurationen, die eine schlechte Benutzererfahrung zur Folge haben könnten.
    

    > [!NOTE]
    > Ausführliche Informationen zur <STRONG>EnableMultiviewJoin</STRONG>-Einstellung finden Sie unter <A href="lync-server-2013-configuring-gallery-view.md">Konfigurieren der Katalogansicht</A>.



  - **MaxVideoConferencingResolution**   Dieser Parameter wird für Lync Server 2013-Clients in Lync Server 2013-Konferenzen nicht mehr verwendet. Bei Lync Server 2013-Konferenzen werden die weiter oben in diesem Abschnitt beschriebenen Bitrate-Steuerungen verwendet. Diese Einstellung wird weiterhin für Clients von Vorversionen verwendet, die einer Lync Server 2013-Konferenz beitreten. Dieser Parameter bestimmt die maximale zulässige Auflösung für Clients von Vorversionen in Konferenzen, die von auf Lync Server 2013 verwalteten Benutzern organisiert werden. Dies bedeutet, dass Clients von Vorversionen so behandelt werden, als befänden sie sich in vorherigen Versionen von Lync Server oder Office Communications Server.

Überprüfen Sie zusätzlich zu den für Benutzer geltenden Einstellungen für Konferenzrichtlinien die Medienkonfigurationseinstellungen. Sie können diese Einstellungen mithilfe eines der folgenden Cmdlets anzeigen oder ändern:

  - **Get-CsMediaConfiguration**

  - **Set- CsMediaConfiguration**

  - **New- CsMediaConfiguration**

Überprüfen Sie die folgenden Einstellungen:

  - **MaxVideoRateAllowed**   Diese Einstellung für einzelne Pools gibt die Höchstrate an, mit der Videosignale an die Clientendpunkte übermittelt werden. Sie gilt nur für vorige Versionen von Lync Server-Clients.
    

    > [!NOTE]
    > Lync Server 2013-Clients ignorieren diese Einstellung und verwenden stattdessen die Einstellung "TotalReceiveVideoBitRateKb" in der Konferenzrichtlinie.

    
    Der Standardwert ist HD720P. Gültige Werte sind HD720p15M, VGA600K und CIF250K.
    
    Beispiel: Wenn Sie 1.500 KBit/s angeben, können alle Clients von Vorversionen im Pool in Konferenzen mit zwei oder mehr Teilnehmern bis zu 1.500 KBit/s an Videoinhalten empfangen.

Die folgenden Verfahren sind Beispiele für die Verwendung von Lync Server-Verwaltungsshell zur Bearbeitung der in diesem Abschnitt beschriebenen Einstellungen.

## So ändern Sie die Einstellungen der Konferenzrichtlinie für Videos

1.  Starten der Lync Server-Verwaltungsshell: Klicken Sie auf **Start**, zeigen Sie auf **Alle Programme** und dann auf **Microsoft Lync Server 2013**, und klicken Sie anschließend auf **Lync Server-Verwaltungsshell**.

2.  Führen Sie an der Befehlszeile das folgende Cmdlet aus, um die Konferenzrichtlinie zu bearbeiten:
    
        Set-CsConferencingPolicy -Identity Pool01ConferencingPolicy -VideoBitRateKb 2000 -TotalReceiveVideoBitRateKb 2000 

## So ändern Sie die Medienkonfiguration für Clients von Vorversionen

1.  Starten der Lync Server-Verwaltungsshell: Klicken Sie auf **Start**, zeigen Sie auf **Alle Programme** und dann auf **Microsoft Lync Server 2013**, und klicken Sie anschließend auf **Lync Server-Verwaltungsshell**.

2.  Führen Sie an der Befehlszeile das folgende Cmdlet aus, um die Medienklonfiguration zu bearbeiten:
    
        Set-CsMediaConfiguration -Identity site:Redmond01 -MaxVideoRateAllowed CIF250K

