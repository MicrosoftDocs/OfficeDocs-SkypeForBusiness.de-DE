---
title: 'Lync Server 2013: Definieren der Anforderungen für Konferenzen'
TOCTitle: Definieren der Anforderungen für Konferenzen
ms:assetid: 5c83e268-22bf-42b2-bac3-3237b5e02e03
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ204935(v=OCS.15)
ms:contentKeyID: 49294131
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Definieren der Anforderungen für Konferenzen in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2012-09-30_

Wenn Sie festlegen, welche Konferenzfunktionen bereitgestellt werden sollen, müssen Sie überlegen, welche Funktionen von Ihren Benutzern genutzt werden sollen und welche Netzwerkbandbreite zur Verfügung steht. Die nachfolgenden Fragen führen Sie durch den Konferenzplanungsprozess und helfen Ihnen, herauszufinden, welche Konferenzfunktionen aufgrund der Anforderungen Ihrer Organisation benötigt werden.

  - **Sollen Webkonferenzfunktionen bereitgestellt werden, die eine gemeinsame Verwendung von Dokumenten und Anwendungen umfassen?**
    
    Wenn ja, müssen Sie Konferenzen für Ihren Front-End-Poolim Microsoft Lync Server 2013, Planungstool oder im Topologie-Generator aktivieren. Durch das Aktivieren von Konferenzen werden sowohl Webkonferenzen als auch A/V-Konferenzen aktiviert.
    
    Bei der Anwendungsfreigabe wird eine höhere Netzwerkbandbreite als bei der Dokumentzusammenarbeit benötigt und belegt. Lync Server 2013 stellt einen Drosselungsmechanismus bereit, mit dem die einzelnen Anwendungsfreigabesitzungen kontrolliert werden können. In der Standardeinstellung ist für jede Sitzung 1,5 KB/s festgelegt.
    
    Wenn Sie die Anwendungsfreigabe nicht aktivieren, die Funktion zur Dokumentzusammenarbeit jedoch bereitstellen möchten, können Sie die Konferenzfunktionen aktivieren und die Anwendungsfreigabe mithilfe von Besprechungsrichtlinien deaktivieren. Nähere Informationen über das Konfigurieren von Besprechungsrichtlinien finden Sie unter [Konferenzrichtlinien in Lync Server 2013](lync-server-2013-conferencing-policies.md).
    
    Um Benutzern das Freigeben von PowerPoint-Präsentationen zu ermöglichen, müssen Sie Office Web Apps-Server konfigurieren. Nähere Informationen zum Konfigurieren von Office Web Apps-Server finden Sie unter [Konfigurieren der Integration mit Office Web Apps Server und Lync Server 2013](lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md).

  - **Sollen A/V-Konferenzen aktiviert werden?**
    
    Wenn ja, müssen Sie Konferenzen für Ihren Front-End-Poolim Lync Server 2013, Planungstool oder im Topologie-Generator aktivieren. Durch das Aktivieren von Konferenzen werden sowohl Webkonferenzen als auch A/V-Konferenzen aktiviert.
    
    Für A/V-Konferenzen ist eine höhere Netzwerkbandbreite erforderlich als für Webkonferenzen (diese umfassen Dokumentzusammenarbeit und Anwendungsfreigabe). Wenn Sie A/V-Konferenzen nicht aktivieren, das Feature für Webkonferenzen jedoch bereitstellen möchten, können Sie die Konferenzfunktionen aktivieren und A/V-Konferenzen mithilfe von Besprechungsrichtlinien deaktivieren.
    
    Wenn Sie Audiokonferenzen, jedoch keine Videokonferenzen zulassen möchten, können Sie die A/V-Konferenzfunktion aktivieren und Videokonferenzen mithilfe von Besprechungsrichtlinien verhindern. Alternativ können Sie A/V-Konferenzen aktivieren und das Starten von oder Teilnehmen an A/V-Konferenzen nur für bestimmte Benutzer zulassen.
    

    > [!NOTE]
    > Enterprise-VoIP wird für A/V-Konferenzen nicht benötigt. Wenn Sie A/V-Konferenzen aktivieren, können Benutzer ihren Konferenzen Audiofunktionen hinzufügen, falls sie über entsprechende Geräte verfügen. Dies gilt auch bei Verwendung eines Nebenstellensystems als Telefonlösung.



  - **Sollen Benutzer bei Verwendung eines Festnetztelefons am Audioteil von Konferenzen teilnehmen können?**
    
    Wenn ja, stellen Sie Einwahlkonferenzen bereit, und aktivieren Sie sie. Eingeladene Benutzer innerhalb und außerhalb Ihrer Organisation können anschließend unter Verwendung eines Festnetztelefons am Audioteil von Konferenzen teilnehmen.

  - **Möchten Sie externen Benutzern mit Lync Server 2013-Clients den Beitritt zu den von Ihnen erstellten Konferenztypen ermöglichen?**
    
    Wenn ja, wird empfohlen, Edgeserver bereitzustellen. Indem Sie externen Benutzern die Teilnahme an Ihren Besprechungen gestatten, maximieren Sie Ihre Investition in Lync Server 2013. Auf diese Weise können etwa Benutzer mit Laptops, auf denen Lync Server 2013 ausgeführt wird, von einem beliebigen Ort (zu Hause, am Flughafen oder beim Kunden) aus an einer Konferenz teilnehmen.
    
    Wenn Sie Edgeserver bereitstellen, können Sie zudem Partnerverbundbeziehungen mit anderen Organisationen – z. B. Ihren Kunden oder Lieferanten – einrichten, sodass Benutzer dieser Organisationen einfacher mit Ihren Benutzern zusammenarbeiten können.
    
    Nähere Informationen zur Bereitstellung von Edgeserver finden Sie unter [Planen des Zugriffs externer Benutzer in Lync Server 2013](lync-server-2013-planning-for-external-user-access.md) und unter [Bereitstellen des Zugriffs durch externe Benutzer in Lync Server 2013](lync-server-2013-deploying-external-user-access.md). Nähere Informationen über das Aktivieren des externen Zugriffs für Office Web Apps-Server finden Sie unter [Veröffentlichen von Office Web Apps Server in Lync Server 2013 mithilfe eines Reverseproxyservers](lync-server-2013-publishing-office-web-apps-server-using-a-reverse-proxy-server.md).

  - **Möchten Sie die Clients kontrollieren, die Lync Server 2013-Besprechungen beitreten können?**
    
    Wenn ja, wird empfohlen, die Besprechungsseite so zu konfigurieren, dass nur die Clientoptionen ausgewählt werden können, die auch unterstützt werden sollen. Immer, wenn ein Benutzer auf einen Link klickt, um einer geplanten Besprechung beizutreten, untersucht Lync Server 2013, ob bereits ein Client auf dem Computer installiert ist. Anschließend wird der Standardclient gestartet, und die Seite für den Besprechungsbeitritt mit Links zu alternativen Clients wird geöffnet. Auf der Seite für den Besprechungsbeitritt finden Sie immer die Option zur Verwendung von Microsoft Lync Web App. Ferner können Sie entscheiden, ob Links für Teilnehmer sowie für Vorversionen von Communicator eingeschlossen werden sollen. Nähere Informationen finden Sie unter [Konfigurieren der Seite für den Besprechungsbeitritt in Lync Server 2013](lync-server-2013-configuring-the-meeting-join-page.md).

## In diesem Abschnitt

  - [Webkonferenzanforderungen](lync-server-2013-web-conferencing-requirements.md)

  - [Anforderungen für A/V-Konferenzen](lync-server-2013-a-v-conferencing-requirements.md)

  - [Anforderungen für Einwahlkonferenzen in Lync Server 2013](lync-server-2013-dial-in-conferencing-requirements.md)

## Siehe auch

#### Weitere Ressourcen

[Planen von Konferenzen in Lync Server 2013](lync-server-2013-planning-for-conferencing.md)  
[Prüfliste zur Bereitstellung für Konferenzen in Lync Server 2013](lync-server-2013-deployment-checklist-for-conferencing.md)

