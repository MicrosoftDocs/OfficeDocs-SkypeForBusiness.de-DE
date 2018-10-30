---
title: 'Lync Server 2013: Definieren und Konfigurieren einer Topologie im Topologie-Generator'
TOCTitle: Definieren und Konfigurieren einer Topologie im Topologie-Generator
ms:assetid: 99231ff5-1c21-432b-ad65-8675fcd484f9
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg398788(v=OCS.15)
ms:contentKeyID: 49294849
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Definieren und Konfigurieren einer Topologie für Lync Server 2013 im Topologie-Generator

 

_**Letztes Änderungsdatum des Themas:** 2013-02-21_

Für die Ausführung des Topologie-Generators zum Definieren einer neuen oder zum Ändern einer vorhandenen Topologie ist keine Mitgliedschaft in einer lokalen Administratorgruppe oder einer Domänengruppe mit besonderen Rechten erforderlich. Der Topologie-Generator leitet Sie durch die notwendigen Schritte zum Definieren Ihrer Topologie für einen Front-End-Pool der Enterprise Edition oder der Standard Edition, je nach Konfigurationsanforderungen.

Sie müssen den Topologie-Generator zum Abschließen und Veröffentlichen der Topologie verwenden, bevor Sie Lync Server 2013 auf Servern installieren können. Das folgende Verfahren umfasst die zum Definieren einer neuen Topologie erforderlichen Schritte.

## So definieren Sie eine Topologie

1.  Starten des Topologie-Generators: Klicken Sie auf **Start**, zeigen Sie auf **Alle Programme** und dann auf **Microsoft Lync Server 2013**, und klicken Sie anschließend auf **Lync Server-Topologie-Generator**.

2.  Wählen Sie im Topologie-Generator die Option **Neue Topologie** . Sie werden aufgefordert, einen Speicherort und einen Dateinamen zum Speichern der Topologie anzugeben. Geben Sie der Topologiedatei einen aussagekräftigen Namen, und übernehmen Sie die Standarderweiterung ".tbxml". Klicken Sie auf **OK** .

3.  Navigieren Sie zu dem Speicherort, in dem die XML-Datei der neuen Topologie gespeichert werden soll, geben Sie einen Namen für die Datei ein, und klicken Sie dann auf **Speichern** .

4.  Geben Sie auf der Seite **Primäre Domäne definieren** den Namen der primären SIP-Domäne für Ihre Organisation ein, und klicken Sie dann auf **Weiter** .

5.  Geben Sie auf der Seite **Weitere unterstützte Domänen angeben** gegebenenfalls die Namen weiterer Domänen ein, und klicken Sie anschließend auf **Weiter** .

6.  Geben Sie auf der Seite **Ersten Standort definieren** einen Namen und eine Beschreibung für den ersten Standort ein, und klicken Sie dann auf **Weiter** .

7.  Geben Sie auf der Seite **Standortdetails angeben** die Standortinformationen für den Standort ein, und klicken Sie dann auf **Weiter** .

8.  Stellen Sie auf der Seite **Neue Topologie erfolgreich definiert** sicher, dass das Kontrollkästchen **Assistent für neues Front-End öffen, wenn dieser Assistent geschlossen wird** aktiviert ist, und klicken Sie auf **Fertig stellen** .

Nachdem Sie die Topologie definiert und gespeichert haben, definieren Sie anhand des Assistenten für neue Front-Ends einen Front-End-Pool oder einen Standard Edition-Server für Ihren Standort. Ausführliche Informationen finden Sie unter [Definieren und Konfigurieren eines Front-End-Pools oder Standard Edition-Servers in Lync Server 2013](lync-server-2013-define-and-configure-a-front-end-pool-or-standard-edition-server.md).

