---
title: 'Lync Server 2013: Hinzufügen von Zweigstellenstandorten zur Topologie'
TOCTitle: Hinzufügen von Zweigstellenstandorten zur Topologie
ms:assetid: b9c35fb0-0081-4aeb-8f95-ac2fcc6c3335
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg412905(v=OCS.15)
ms:contentKeyID: 49295208
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Hinzufügen von Zweigstellenstandorten zur Topologie in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2012-10-05_

Zweigstellenstandorte repräsentieren physische Zweigstellenbüros, die über einen WAN-Link mit Ihren Hauptbüros verbunden sind. Führen Sie dieses Verfahren am zentralen Standort aus, um einen Zweigstellenstandort zu Ihrer Lync-Topologie hinzuzufügen.

## So fügen Sie Zweigstellenstandorte zu einer Topologie hinzu

1.  Klicken Sie auf **Start** , **Alle Programme** , **Microsoft Lync Server** und anschließend auf **Lync Server-Topologie-Generator** .

2.  Erweitern Sie den zentralen Standort in der Konsolenstruktur, klicken Sie mit der rechten Maustaste auf **Zweigstellenstandorte** , und klicken Sie dann auf **Neuer Zweigstellenstandort** .

3.  Klicken Sie im Dialogfeld **Neue Zweigniederlassung definieren** auf **Name** und geben Sie den Namen für die Zweigniederlassung ein.

4.  (Optional) Klicken Sie auf **Beschreibung** , und geben Sie eine aussagekräftige Beschreibung für die Zweigniederlassung ein.

5.  Klicken Sie auf **Weiter** .

6.  (Optional) Führen Sie im nächsten Dialogfeld **Neue Zweigniederlassung definieren** einen der folgenden Schritte aus:
    
      - Klicken Sie auf **Ort** , und geben Sie den Namen der Stadt ein, in der sich die Zweigniederlassung befindet.
    
      - Klicken Sie auf **Bundesland/Kanton** , und geben Sie den Namen des Bundeslands bzw. Kantons ein, in dem sich die Zweigniederlassung befindet.
    
      - Klicken Sie auf **Ländercode** , und geben Sie den zweistelligen Ländercode für das Land ein, in dem sich die Zweigniederlassung befindet.

7.  Klicken Sie auf **Weiter** , und führen Sie einen der folgenden Schritte aus:
    
      - Stellen Sie bei Verwendung einer Survivable Branch-Anwendung oder eines Servers an diesem Standort sicher, dass das Kontrollkästchen **Assistent für neue Survivable Branch Appliance oder neuen Survivable Branch Server öffnen, wenn dieser Assistent geschlossen wird** aktiviert ist, klicken Sie auf **Fertig stellen** , und befolgen Sie die Anweisungen des Assistenten, der geöffnet wird. Ausführliche Informationen zu diesem Assistenten finden Sie unter [Definieren einer Survivable Branch Appliance oder eines Survivable Branch Servers in Lync Server 2013](lync-server-2013-define-a-survivable-branch-appliance-or-server.md).
    
      - Wenn Sie an diesem Standort keine Survivable Branch-Anwendung bzw. keinen Server verwenden, deaktivieren Sie das Kontrollkästchen **Assistent für neue Survivable Branch Appliance oder neuen Survivable Branch Server öffnen, wenn dieser Assistent geschlossen wird** , und klicken Sie anschließend auf **Fertig stellen** .

8.  Wiederholen Sie die oben beschriebenen Schritte für jeden Zweigniederlassung, die der Topologie hinzugefügt werden soll.

**Nächster Schritt:**

Für Survivable Branch Appliances oder Survivable Branch Server: [Definieren einer Survivable Branch Appliance oder eines Survivable Branch Servers in Lync Server 2013](lync-server-2013-define-a-survivable-branch-appliance-or-server.md)

Für PSTN-Anbindung ohne Ausfallsicherheit: [Definieren eines PSTN-Gateways für eine Zweigstelle in Lync Server 2013](lync-server-2013-define-a-pstn-gateway-for-a-branch-site.md), [Konfigurieren eines Trunks mit Medienumgehung in Lync Server 2013](lync-server-2013-configure-a-trunk-with-media-bypass.md) oder [Konfigurieren eines Trunks ohne Medienumgehung in Lync Server 2013](lync-server-2013-configure-a-trunk-without-media-bypass.md)

