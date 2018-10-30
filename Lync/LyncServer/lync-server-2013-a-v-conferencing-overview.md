---
title: Übersicht über A/V-Konferenzen
TOCTitle: Übersicht über A/V-Konferenzen
ms:assetid: 9583de87-4618-4a99-a47a-45e8cc4cc221
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ619186(v=OCS.15)
ms:contentKeyID: 49294799
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Übersicht über A/V-Konferenzen

 

_**Letztes Änderungsdatum des Themas:** 2016-12-08_

A/V-Konferenzen ermöglichen Echtzeit-Audio- und -Videokonferenzen zwischen Ihren Benutzern. Wenn Sie die Konferenzfunktion bereitstellen, können Sie entweder sowohl Webkonferenzen als auch A/V-Konferenzen oder nur Webkonferenzen aktivieren.

Zum Planen von A/V-Konferenzen müssen Sie die erforderliche Netzwerkbandbreite für den Typ der Konferenzmedien kennen, die in Ihrer Organisation verwendet werden. Dies könnten z. B. Audio, Video und Panoramavideo sein.

Bevor Sie Benutzer für A/V-Konferenzen aktivieren, müssen Sie sicherstellen, dass die resultierende Last in Ihrem Netzwerk verarbeitet werden kann. Eine zu geringe Netzwerkbandbreite kann zu einem stark beeinträchtigten Benutzererlebnis führen. Für die Verwaltung der von A/V-Konferenzen verwendeten Netzwerkbandbreite können Sie die Anrufsteuerung (CAC) verwenden. Dies ist für eingeschränkte Netzwerke wichtig, beispielsweise bei Verbindungen mit beschränkter Bandbreite zwischen Zentrale und Niederlassungen. Ausführliche Informationen finden Sie unter [Übersicht über die Anrufsteuerung in Lync Server 2013](lync-server-2013-overview-of-call-admission-control.md). Ausführliche Informationen zu den Anforderungen an Medienbandbreiten finden Sie unter [Anforderungen hinsichtlich der Netzwerkbandbreite für Mediendatenverkehr](lync-server-2013-network-bandwidth-requirements-for-media-traffic.md).

Bei Bereitstellung der Audiokonferenzfunktion in Ihrem Netzwerk benötigen Ihre Benutzer Audiogeräte (z. B. Headsets), um an einer Audiokonferenz teilzunehmen. Wenn Sie Videokonferenzen bereitstellen, benötigen die Benutzer Videogeräte, wie Webcams. Wir empfehlen für alle Gerätetypen die Verwendung von UC-Geräten (Unified Communications), die durch Microsoft zertifiziert wurden, um eine optimale Benutzererfahrung sicherzustellen. Ausführliche Informationen zu UC-zertifizierten Geräten finden Sie im Beitrag zu Telefonen und Geräten für Lync unter [http://go.microsoft.com/fwlink/?linkid=263861\&clcid=0x407](http://go.microsoft.com/fwlink/?linkid=263861%26clcid=0x407). Für Audio- oder Videogeräte sollten Sie die Bereitstellung der Geräte und die Schulung der Benutzer unbedingt einplanen.

In den folgenden Abschnitten werden die Funktionen für Audio- und Videokonferenzen beschrieben. Außerdem finden Sie Informationen zur Bandbreitenverwaltung und zur Auswahl geeigneter Clients.

## Audiokonferenzfunktionen

Lync Server 2013 bietet verschiedene Funktionen, die Sie für die Konfiguration des Audiokonferenzerlebnisses des Benutzers nutzen können. Hierzu gehören:

  - **Stummschaltung der Teilnehmer**    Der Referent kann mit dieser Einstellung alle Audioteilnehmer der Konferenz stummschalten und die Konferenz so in einen Modus versetzen, in dem die Telnehmer die Stummschaltung nicht selbst aufheben können.

  - **Ansagen beim Beitreten und Verlassen**   Wenn Sie Einwahlkonferenzen aktiviert haben, können Referenten über diese Einstellung Ansagen beim Beitreten und Verlassen ein- oder ausschalten, um während der Konferenz Ablenkungen zu vermeiden.

  - **Einen Benutzer über eine ausgehende Telefonverbindung hinzufügen**   Referenten und Teilnehmer, die dazu berechtigt sind, können PSTN-Nummern zu Konferenzen hinzufügen, über die die Konferenz eine ausgehende Telefonverbindung zu diesen Nummern herstellt.

## Videokonferenzfunktionen

Lync Server 2013 bietet verschiedene Funktionen, die Sie für die Konfiguration des Videokonferenzerlebnisses des Benutzers verwenden können. Hierzu gehören:

  - **Profilfotoansicht**   In Videokonferenzen, an denen mehr als zwei Personen teilnehmen, sehen die Benutzer automatisch alle Teilnehmer der Konferenz. Wenn die Konferenz mehr als fünf Teilnehmer hat, werden in der ersten Zeile die Videos der aktivsten Teilnehmer angezeigt und für die übrigen Teilnehmer lediglich Fotos. Die Videoaushandlung ist standardmäßig aktiviert. Ausführliche Informationen zur Konfiguration und Deaktivierung der Videoaushandlung finden Sie unter [Konfigurieren der Videobandbreite in Lync Server 2013](lync-server-2013-configuring-video-bandwidth.md).

  - **Panoramavideo**   Wenn im Konferenzraum ein Round Table-Videokonferenzgerät installiert ist , bietet diese Funktion eine vollständige 360-Grad-Ansicht des Konferenzraums. Panoramavideo ist nur mit Round Table verfügbar.

  - **Modus Nur-Referentenvideo**   Referenten können Besprechungen so konfigurieren, dass nur das Video des Referenten angezeigt wird. Dies verhindert bei großen Besprechungen Ablenkungen, wenn mehrere Videostreams verfügbar und mit verschiedenen Quellen verbunden sind. Dieser Modus wird auch auf Videos angewendet, die durch Round Table-Geräte aufgenommen und bereitgestellt werden.

  - **HD-Video**   Benutzer können Auflösungen bis zu HD 1080P bei Anrufen mit zwei Teilnehmern und Konferenzen mit mehreren Teilnehmern anzeigen.

  - **Video Spotlight**   Referenten können die Besprechung so konfigurieren, dass die Teilnehmer der Konferenz nur das Video eines ausgewählten Teilnehmers, der eine Videoquelle ist, sehen. Dieser Modus wird auch auf Videos angewendet, die durch Round Table-Geräte aufgenommen und bereitgestellt werden.

