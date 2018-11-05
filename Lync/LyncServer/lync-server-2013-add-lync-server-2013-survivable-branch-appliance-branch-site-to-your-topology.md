---
title: 'Lync Server 2013: Hinzufügen eines Zweigstellenstandorts mit einer Lync Server 2013 Survivable Branch Appliance zu einer Topologie'
TOCTitle: Hinzufügen eines Zweigstellenstandorts mit einer Lync Server 2013 Survivable Branch Appliance zu einer Topologie
ms:assetid: d3142a37-4606-456d-8ea9-6cc0e51e55f3
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ721896(v=OCS.15)
ms:contentKeyID: 49890958
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Hinzufügen eines Zweigstellenstandorts mit einer Lync Server 2013 Survivable Branch Appliance zu einer Topologie

 

_**Letztes Änderungsdatum des Themas:** 2012-10-07_

Microsoft Lync Server 2013Survivable Branch-Anwendungen (SBA) kann einem Microsoft Lync Server 2010- Front-End-Pool nicht als Sicherungsregistrierungsstelle zugeordnet werden. SBA muss einem Microsoft Lync Server 2013- Front-End-Pool zugeordnet werden. Bei diesen Schritten wird von einer Microsoft Lync Server 2013 SBA ausgegangen. Führen Sie dieses Verfahren am zentralen Standort aus.

## So fügen Sie einer Topologie Zweigniederlassungen mit Microsoft Lync Server 2013 hinzu

1.  Starten des Topologie-Generators: Klicken Sie auf **Start**, zeigen Sie auf **Alle Programme** und dann auf **Microsoft Lync Server 2013**, und klicken Sie anschließend auf **Lync Server-Topologie-Generator**.

2.  Erweitern Sie den zentralen Standort in der Konsolenstruktur, erweitern Sie **Zweigniederlassungen** , und klicken Sie dann auf **Neue Zweigniederlassung** .

3.  Klicken Sie im Dialogfeld **Neue Zweigniederlassung definieren** auf **Name** , und geben Sie einen Namen für die neue Zweigniederlassung ein.

4.  (Optional) Klicken Sie auf **Beschreibung** , und geben Sie eine aussagekräftige Beschreibung für die Zweigniederlassung ein.

5.  Klicken Sie auf **Weiter** .

6.  (Optional) Führen Sie im nächsten Dialogfeld **Neue Zweigniederlassung definieren** einen der folgenden Schritte aus:
    
      - Klicken Sie auf **Ort** , und geben Sie den Namen der Stadt ein, in der sich die Zweigniederlassung befindet.
    
      - Klicken Sie auf **Bundesland/Kanton** , und geben Sie den Namen des Bundeslands bzw. Kantons ein, in dem sich die Zweigniederlassung befindet.
    
      - Klicken Sie auf **Ländercode** , und geben Sie den zweistelligen Ländercode für das Land ein, in dem sich die Zweigniederlassung befindet.

7.  Klicken Sie auf **Weiter** , und führen Sie einen der folgenden Schritte aus:
    
      - Bei Verwendung einer Survivable Branch-Anwendung oder eines Survivable Branch-Servers an diesem Standort sollten Sie unbedingt das Kontrollkästchen **Assistenten für neue Survivable Branch Appliance öffnen, wenn der Assistent geschlossen wird** aktivieren.
    
      - Wenn Sie an diesem Standort keine Survivable Branch-Anwendung oder keinen Survivable Branch-Server verwenden, deaktivieren Sie das Kontrollkästchen **Assistenten für neue Survivable Branch Appliance öffnen, wenn der Assistent geschlossen wird** .
    
      - Klicken Sie auf **Fertig stellen** , und befolgen Sie die Anweisungen im Assistenten, der geöffnet wird. Ausführliche Informationen zu diesem Assistenten finden Sie unter [Definieren einer Survivable Branch Appliance oder eines Survivable Branch Servers in Lync Server 2013](lync-server-2013-define-a-survivable-branch-appliance-or-server.md).

8.  Wiederholen Sie die oben beschriebenen Schritte für jeden Zweigniederlassung, die der Topologie hinzugefügt werden soll.

## Siehe auch

#### Aufgaben

[Definieren einer Survivable Branch Appliance oder eines Survivable Branch Servers in Lync Server 2013](lync-server-2013-define-a-survivable-branch-appliance-or-server.md)  
[Definieren eines PSTN-Gateways für eine Zweigstelle in Lync Server 2013](lync-server-2013-define-a-pstn-gateway-for-a-branch-site.md)  
[Konfigurieren eines Trunks mit Medienumgehung in Lync Server 2013](lync-server-2013-configure-a-trunk-with-media-bypass.md)  
[Konfigurieren eines Trunks ohne Medienumgehung in Lync Server 2013](lync-server-2013-configure-a-trunk-without-media-bypass.md)

