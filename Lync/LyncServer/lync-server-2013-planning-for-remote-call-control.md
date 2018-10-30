---
title: 'Lync Server 2013: Planen der Remoteanrufsteuerung'
TOCTitle: Planen der Remoteanrufsteuerung
ms:assetid: 688a0328-1aa7-449f-b5f7-98c876112ed2
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg558658(v=OCS.15)
ms:contentKeyID: 49294276
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Planen der Remoteanrufsteuerung in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2012-09-05_

Die Unterstützung von Szenarien mit Remoteanrufsteuerung in Lync Server 2013 ermöglicht es Benutzern, ihre Nebenstellentelefone mithilfe von Lync 2013 auf ihren Desktopcomputern zu steuern. In diesem Abschnitt werden die Remoteanrufsteuerungsfunktionen sowie die Anforderungen für die Bereitstellung der Remoteanrufsteuerung beschrieben.

Durch die Integration von Nebenstellenanlagen und Lync Server 2013 können Benutzer, die für Remoteanrufsteuerung aktiviert sind, ihre Nebenstellentelefone über die Benutzeroberfläche von Lync 2013 auf die folgenden Weisen steuern:


> [!NOTE]
> Welche Remoteanrufsteuerungsfunktionen für den Benutzern letztendlich verfügbar sind, hängt von den Funktionen der Nebenstellenanlage ab, die zum Hosten des Nebenstellentelefons eines Benutzers verwendet wird.



  - Tätigen eines ausgehenden Anrufs

  - Beantworten eines eingehenden Anrufs

  - Beantworten eines eingehenden Anrufs mit einer Sofortnachricht
    

    > [!NOTE]
    > Dies ist möglich, wenn die Telefonnummer des Anrufers einer Sofortnachrichtenadresse in der globalen Adressliste Ihrer Organisation, in der Lync-Kontaktliste des Anrufempfängers oder in der Organisation eines Verbundpartners zugeordnet werden kann.



  - Weiterleiten eines Anrufs

  - Weiterleiten eines eingehenden Anrufs

  - Halten von Anrufen

  - Wechseln zwischen mehreren gleichzeitigen Anrufen

  - Beantworten eines zweiten Anrufs, nachdem bereits ein Anruf entgegengenommen wurde (Anklopffunktion)

  - DTMF-Ziffern (Dial Dual-Tone Multifrequency, Mehrfrequenzverfahren)

  - Eingabe von Notizen im Fenster "Unterhaltung" in Microsoft Office OneNote

Wenn ein Benutzer für die Remoteanrufsteuerung aktiviert ist, stellt Lync 2013 zudem die folgenden Anrufinformationen für den Benutzer bereit:

  - Anzeige des Namens des Anrufers, wenn die Telefonnummer des Anrufers in der Microsoft Office Outlook-Kontaktliste eines Benutzers steht, der für Remoteanrufsteuerung aktiviert ist, oder in der Lync-Kontaktliste oder in der globalen Adressliste Ihrer Organisation vorhanden ist.

  - Vergangene eingehende und ausgehende Anrufe, die im Ordner "Unterhaltungsverlauf" in Outlook gespeichert sind.

  - Benachrichtigungen zu verpassten Anrufen, die an den Outlook-Posteingang des Benutzers gesendet werden. Diese Benachrichtigungen werden jedoch nur generiert, wenn bei Eingang des Anrufs Lync ausgeführt wird.

## Remoteanrufsteuerung und Enterprise-VoIP

Obgleich die Funktionen für Remoteanrufsteuerung und die Enterprise-VoIP-Funktionen separat sind und Benutzer nicht für beide aktiviert werden können, bietet Enterprise-VoIP eine Untermenge an Funktionen, die auch den Benutzern zur Verfügung stehen, die für Remoteanrufsteuerung aktiviert sind. Wenn Enterprise-VoIP bereitgestellt ist, können für Remoteanrufsteuerung aktivierte Benutzer über Lync auf die folgenden Enterprise-VoIP-Funktionen zugreifen:

  - Tätigen und Empfangen von Audioanrufen an bzw. von anderen Lync-Clients

  - Teilnehmen am Audioteil einer Konferenz, die von einem für Enterprise-VoIP aktivierten Benutzer erstellt wurde

## In diesem Abschnitt

  - [Bereitstellungsaufgaben für die Remoteanrufsteuerung in Lync Server 2013](lync-server-2013-deployment-tasks-for-remote-call-control.md)

