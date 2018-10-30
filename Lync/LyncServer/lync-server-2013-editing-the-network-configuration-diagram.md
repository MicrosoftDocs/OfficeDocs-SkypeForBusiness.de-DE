---
title: Bearbeiten des Netzwerkkonfigurationsdiagramms
TOCTitle: Bearbeiten des Netzwerkkonfigurationsdiagramms
ms:assetid: 47425ab1-5645-4d6f-b202-64bcce43e3ef
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg558643(v=OCS.15)
ms:contentKeyID: 52056325
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Bearbeiten des Netzwerkkonfigurationsdiagramms

 

_**Letztes Änderungsdatum des Themas:** 2013-02-21_

Die Hauptaufgabe, die der für den Entwurf verantwortliche Benutzer im Lync Server 2013, Planungstool ausführt, besteht im Definieren der IP-Adressen und vollqualifizierten Domänennamen (Fully Qualified Domain Names, FQDNs) für die Einträge im Netzwerkdiagramm. Die auf dieser Seite eingegebenen Informationen werden in die Berichte und andere Informationen übertragen, die im Planungstool enthalten sind.

![Planungstool – Netzwerk (Diagramm)](images/Gg558643.eeabee2d-698c-4b79-baa5-caa4cfb7edb3(OCS.15).jpg "Planungstool – Netzwerk (Diagramm)")

Das Planungstool erstellt ein Netzwerkdiagramm mit Standardtext für IP-Adressen und FQDNs.

So bearbeiten Sie das Netzwerkdiagramm und geben Werte ein

1.  Wählen Sie einen Abschnitt des Netzwerks aus, den Sie zuerst bearbeiten möchten. Doppelklicken Sie z. B. auf den Text **access1.contoso.net**. Geben Sie im nun geöffneten Dialogfeld den tatsächlichen FQDN für den Server "access1.contoso.net" ein, und ersetzen Sie die IP-Adresse 131.107.155.1 durch die tatsächliche IP-Adresse.

2.  Klicken Sie auf **OK**, um die Einträge zu speichern.

3.  Fahren Sie mit der Bearbeitung von IP-Adressen und FQDNs fort, und geben Sie virtuelle IP-Adressen für Hardwaregeräte zum Lastenausgleich oder Servereinträge für einen DNS-Lastenausgleich (Domain Name System) für Server in Pools an.

Eine nützliche Funktion des Planungstools ist die, dass ein Bereich von IP-Adressen und Serverhostnamen inkrementell zugewiesen werden kann. Auf diese Weise muss der für den Entwurf verantwortliche Benutzer die Server in einem Pool nicht einzeln bearbeiten. Beispiel:

1.  Doppelklicken Sie auf die Front-End-Server im Pool. Wählen Sie im nun geöffneten Dialogfeld die Option **Möchten Sie IP-Adressen und FQDN als Startpunkte für alle äquivalenten Server im Cluster verwenden?**.

2.  Beispielsweise lautet der Startwert für den ersten Server "fe0101.contoso.net", und die IP-Adresse ist auf "192.168.21.222" festgelegt.

3.  Geben Sie in **FQDN des Front-End-Servers** den Wert **fe0.contoso.net** ein, geben Sie in **IP-Adresse des Front-End-Servers** die Adresse **192.168.21.131** ein, und klicken Sie auf **OK**.

4.  Die Funktion zur automatischen inkrementellen Erhöhung aktualisiert alle Server im Pool von "fe01" bis "fe06" und alle IP-Adressen von 192.168.21.131 bis 136.

Nachdem Sie die Bearbeitung abgeschlossen haben, speichern Sie die Topologie, indem Sie folgende Schritte ausführen:

Klicken Sie auf **Datei**, und klicken Sie dann auf **Topologie speichern** oder **Topologie speichern unter**, um den im Planungstool erstellten Entwurf zu speichern. Wenn ein Dialogfeld **Planungstool speichern unter** angezeigt wird, geben Sie in **Dateiname** einen Namen für die Datei ein, und klicken Sie dann auf **Speichern**.

## Siehe auch

#### Konzepte

[Bearbeiten des Entwurfs in Lync Server 2013](lync-server-2013-editing-the-design.md)

