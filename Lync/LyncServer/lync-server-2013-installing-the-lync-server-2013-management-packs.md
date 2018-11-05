---
title: Installieren der Lync Server 2013 Management Packs
TOCTitle: Installieren der Lync Server 2013 Management Packs
ms:assetid: b800d4ab-fdc8-4c72-a76a-b78932779fe3
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ205202(v=OCS.15)
ms:contentKeyID: 49295189
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Installieren der Lync Server 2013 Management Packs

 

_**Letztes Änderungsdatum des Themas:** 2016-12-08_

System Center Operations Manager ist von sich aus lediglich in der Lage, einen kleinen Teil des Windows-Betriebssystems zu überwachen. Sie können die Funktionen von System Center Operations Manager jedoch durch Installation von Management Packs erweitern. Diese Software legt fest, welche Elemente System Center Operations Manager überwachen kann, und umfasst Informationen, wie diese Elemente überwacht und wie Benachrichtigungen ausgelöst und berichtet werden sollen. Microsoft Lync Server 2013 umfasst zwei System Center Operations Manager-Management Packs, mit denen folgende Funktionen zur Verfügung gestellt werden:

  - Das Komponenten- und Benutzer-Management Pack (Microsoft.LS.2013.Monitoring.ComponentAndUser.mp) verfolgt Lync Server-Probleme, die in Ereignisprotokollen aufgezeichnet, durch Leistungsindikatoren erfasst oder in den Datenbanken für Kommunikationsdatensätze (Call Detail Records - CDR) oder QoE-Daten (Quality of Experience) protokolliert wurden. Bei schwerwiegenden Problemen kann System Center Operations Manager so konfiguriert werden, dass Administratoren sofort per E-Mail, Sofortnachricht oder SMS benachrichtigt werden. SMS ist die Technologie, die verwendet wird, um Textnachrichten von einem Mobilgerät an ein anderes zu senden.
    

    > [!NOTE]
    > Weitere Informationen zur Konfiguration der Operations Manager-Benachrichtigung finden Sie unter "Benachrichtigung konfigurieren" in der TechNet-Bibliothek unter <A class=uri href="http://go.microsoft.com/fwlink/?linkid=268785%26clcid=0x407">http://go.microsoft.com/fwlink/?linkid=268785&amp;clcid=0x407</A>.



  - Das Active Monitoring Pack (Microsoft.LS.2013.Monitoring.ActiveMonitoring.mp) testet proaktiv wichtige Lync Server-Komponenten wie zum Beispiel das Anmelden beim System, das Austauschen von Sofortnachrichten oder das Tätigen von Anrufen im Telefonfestnetz (Public Switched Telephone Network, PSTN). Diese Tests werden mithilfe der Lync Server-Cmdlets für synthetische Transaktionen durchgeführt. Zum Beispiel wird das **Test-CsIM**-Cmdlet verwendet, um eine Sofortnachrichtenunterhaltung zwischen zwei Testbenutzern zu simulieren. Wenn bei dieser simulierten Nachrichtenunterhaltung ein Fehler auftritt, wird eine Benachrichtigung erzeugt.

Die beiden in Lync Server 2013 enthaltenen Management Packs enthalten eine große Anzahl an Erweiterungen im Vergleich zu den Management Packs, die bei Microsoft Lync Server 2010 verwendet werden. Zum Beispiel ist das Lync Server 2013-Component Management Pack nicht auf die Überwachung von Lync Server beschränkt. Neben der Überwachung von Ereignisprotokollen und Leistungsindikatoren für Lync Server eignet sich das Component Management Pack auch für die Überwachung der Leistung und die Ausgabe von Benachrichtigungen für wichtige Elemente, wie zum Beispiel:

  - **Internetinformationsdienste (IIS)** Benachrichtigungen werden ausgegeben, wenn Internetinformationsdienste offline gehen. Dies ist wichtig, weil die Lync Server-Webdienste von IIS abhängen.

  - **Prozessnutzung** Benachrichtigungen werden ausgegeben, wenn die Systemressourcen (wie zum Beispiel verfügbarer Speicher) knapp werden. Diese Benachrichtigungen werden auch dann ausgegeben, wenn die hohe Systemauslastung nicht auf Lync Server zurückzuführen ist.

  - **Computerausfallereignis** Benachrichtigungen werden ausgegeben, wenn ein Hardware- oder Software-Problem die Serverfähigkeit gefährdet. Zum Beispiel werden Lync Server-Administratoren benachrichtigt, wenn ein Server durch einen Festplattenausfall gefährdet ist.

Die neuen Management Packs verfügen außerdem über eine erweiterte Berichtsfunktion. Die neuen Berichte für Lync Server 2013 umfassen:

  - **Umfassender Szenarioverfügbarkeitsbericht**   Dieser Bericht liefert ausführliche Informationen über die Verfügbarkeit/Betriebszeit für wichtige Lync Server-Dienste wie Registrierung oder Anwesenheit.

  - **Kapazitätsbericht**   Dieser Bericht nutzt Informationen aus Leistungsindikatoren, um Trends bei Systemkomponenten wie Speicherverfügbarkeit und Prozessorverwendung zu veranschaulichen.

  - **Komponentenbericht**   Dieser Bericht listet die wichtigsten Verursacher von Benachrichtigungen gruppiert nach Lync Server-Komponenten auf.

Zusätzlich zu diesen vorgefertigten Berichten berichten die Management Packs für Lync Server 2013 automatisch Benachrichtigungen für Anrufzuverlässigkeit (Metriken ermittelt aus Aufzeichnung von Kommunikationsdatensätzen) und QoE-Status (Metriken ermittelt durch QoE). Wenn die Aufzeichnung von Kommunikationsdatensätzen aktiviert ist, können Sie Anrufzuverlässigkeitsbenachrichtigungen prüfen, in dem Sie folgendes Verfahren aus der System Center Operations Manager-Konsole ausführen:

  - Erweitern Sie **Überwachen**, **Zustand Microsoft Lync Server 2013** und **Anrufzuverlässigkeit und Medienqualität**, und klicken Sie dann auf **Anrufzuverlässigkeit**.

Führen Sie folgendes Verfahren aus der System Center Operations Manager-Konsole aus, um QoE-Benachrichtigungen anzuzeigen:

  - Erweitern Sie **Überwachen**, **Zustand Microsoft Lync Server 2013** und **Anrufzuverlässigkeit und Medienqualität**, und erweitern Sie dann **Medienqualität**.

Die Management Packs für Lync Server 2013 verwenden jetzt die Ermittlung auf Computerebene anstelle des in Microsoft Lync Server 2010 verwendeten zentralen Ermittlungsmechanismus. Das bedeutet, dass jeder System Center-Agent sich im Wesentlichen selbst ermittelt und seine Existenz an den zentraler Verwaltungsserver berichtet. Die Verwendung der Ermittlung auf Computerebene vereinfacht die Verwaltung Ihrer System Center-Infrastruktur und ermöglicht zudem, dass verschiedene Versionen der Lync Server-Management Packs (zum Beispiel Management Packs für Lync Server 2010 und Management Packs für Lync Server 2013) nebeneinander verwendet werden können.

