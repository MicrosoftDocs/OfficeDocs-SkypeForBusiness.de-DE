---
title: 'Lync Server 2013: Ausfallsicherheitsfunktionen für Zweigstellenstandorte'
TOCTitle: Ausfallsicherheitsfunktionen für Zweigstellenstandorte
ms:assetid: 8e3feda5-9a38-4e3c-b808-af29f19c5eb9
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg398715(v=OCS.15)
ms:contentKeyID: 49294710
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Ausfallsicherheitsfunktionen für Zweigstellenstandorte in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2014-02-10_

Wenn Sie Ausfallsicherheit für Zweigstellenstandorte bereitstellen, sollten die folgenden VoIP-Funktionen weiterhin verfügbar sein, wenn die WAN-Leitung zwischen einem Zweigstellenstandort und einem zentralen Standort ausfällt oder der zentrale Standort nicht verfügbar ist.


  - Eingehende und ausgehende PSTN-Anrufe (Public Switched Telephone Network)

  - Enterprise-Anrufe zwischen Benutzern, die sich entweder am selben oder an zwei verschiedenen Standorten befinden

  - Grundlegende Anrufbehandlung, einschließlich Halten, Wiederaufnahme und Übergabe

  - Instant Messaging mit zwei Teilnehmern

  - Anrufweiterleitung, gleichzeitiges Klingeln von Endgeräten, Anrufdelegierung und Teamanrufdienste - jedoch nur, wenn beide Teilnehmer für die Anrufdelegierung (z. B. ein Manager und der Administrator des Managers) oder alle Teammitglieder am selben Standort konfiguriert sind.

  - Kommunikationsdatensätze (KDS)

  - PSTN-Einwahlkonferenzen mit automatischer Konferenzzentrale

  - Voicemailfunktionen, sofern Sie Einstellungen für die Voicemailumleitung konfigurieren. (Ausführliche Informationen finden Sie unter [Anforderungen für die Ausfallsicherheit an Zweigstellenstandorten für Lync Server 2013](lync-server-2013-branch-site-resiliency-requirements.md).)

  - Benutzerauthentifizierung und -autorisierung

Die folgenden Funktionen sind nur verfügbar, wenn es sich bei Ihrer Ausfallsicherheitslösung um eine vollständige Lync Server-Bereitstellung am Zweigstellenstandort handelt:

  - Chat-, Web- und A/V-Konferenzen

  - Anwesenheits- und DND-basiertes Routing (Telefon soll bei eingehenden Anrufen an Ihre Durchwahlnummern mit dem Status "Nicht stören" nicht klingen)

  - Aktualisieren der Einstellungen für die Anrufweiterleitung

  - Reaktionsgruppenanwendung und Anwendung zum Parken von Anrufen

  - Bereitstellung neuer Telefone und Clients, jedoch nur, wenn am Zweigstellenstandort die Bereitstellung von Active Directory-Domänendienste abgeschlossen wurde.

  - 9-1-1 (erweitert) (E9-1-1)
    
    Wenn E9-1-1 bereitgestellt wurde und der SIP-Trunk am zentralen Standort aufgrund eines Ausfalls der WAN-Leitung nicht verfügbar ist, leitet die Survivable Branch-Anwendung E9-1-1-Anrufe an das lokale Gateway der Zweigstelle weiter. Zum Aktivieren dieser Funktion muss die Weiterleitung von Anrufen an das lokale Gateway bei einem WAN-Ausfall in den VoIP-Richtlinien der Zweigstellenbenutzer festgelegt werden.


> [!NOTE]
> SBA (Survivable Branch Office) wird für XMPP nicht unterstützt. Benutzer, die unter einer SBA-Konfiguration verwaltet werden, können keine Chatnachrichten an XMPP-Kontakte senden oder die Anwesenheit dieser Kontakte sehen.


