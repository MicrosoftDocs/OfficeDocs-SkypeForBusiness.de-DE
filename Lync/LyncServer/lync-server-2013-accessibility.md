---
title: Lync Server 2013 Barrierefreiheit
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Accessibility for people with disabilities
ms:assetid: 29c35a47-2513-425c-8b6b-250786573171
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204754(v=OCS.15)
ms:contentKeyID: 48183681
ms.date: 01/15/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e86fbe2c8ac007f81743bd5a5be105421767089e
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "42135642"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="accessibility-in-lync-server-2013"></a>Barrierefreiheit in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2014-10-09_

Microsoft hat es sich zur Aufgabe gemacht, die Handhabung der Produkte und Dienste für jeden möglichst einfach zu gestalten. Die folgenden Abschnitte enthalten Informationen zu den Features, Produkten und Diensten, mit denen die Barrierefreiheit von lync Server 2013 für Personen mit Behinderungen erleichtert wird.

<div>

## <a name="accessibility-features-of-lync-server-2013"></a>Barrierefreiheitsfunktionen von lync Server 2013

Die folgenden Features in lync Server 2013 helfen Benutzern mit Behinderungen, die Barrierefreiheit zu erleichtern:

  - Tastenkombinationen

  - Alternativtext für Abbildungen

Darüber hinaus können einige Barrierefreiheitsfeatures und-Tools von Windows lync Server Benutzern mit Behinderungen zugute kommen. Windows PowerShell Größen-und Farbänderungen bieten Optionen für Barrierefreiheit bei Verwendung der lync Server-Verwaltungsshell. Ausführliche Informationen zu Windows PowerShell Optionen für Barrierefreiheit finden Sie unter "Barrierefreiheit in Windows PowerShell 2,0" in [https://go.microsoft.com/fwlink/p/?linkId=98964](https://go.microsoft.com/fwlink/p/?linkid=98964)der TechNet-Bibliothek unter.

</div>

<span id="BKMK_KeyboardShortcuts"></span>

<div>

## <a name="keyboard-shortcuts"></a>Tastenkombinationen

Sie können Tastenkombinationen für die Interaktion mit der Benutzeroberfläche in lync Server Verwaltungstools und anderen Features verwenden.

Mithilfe von Tastenkombinationen können Sie schnell die folgenden allgemeinen Aufgaben durchführen.


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Aufgabe</th>
<th>Tastenkombination</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Wechseln zwischen Elementen auf der Benutzeroberfläche</p></td>
<td><p>Tab</p></td>
</tr>
<tr class="even">
<td><p>Durchführen der Aktion für das ausgewählte Element, z. B. <strong>Alle anzeigen</strong>, <strong>Alle ausblenden</strong>, oder Öffnen eines Links</p></td>
<td><p>Geben Sie Folgendes ein:</p></td>
</tr>
<tr class="odd">
<td><p>Wechseln vom ausgewählten Element zum nächsten Element auf der Seite oder in einem Menü</p></td>
<td><p>Tab</p></td>
</tr>
<tr class="even">
<td><p>Wechseln vom ausgewählten Element zum vorherigen Element auf der Seite</p></td>
<td><p>UMSCHALT+TAB</p></td>
</tr>
<tr class="odd">
<td><p>Navigieren nach oben, unten, links oder rechts, um auf der Seite oder im Menü ein anderes Element auszuwählen</p></td>
<td><p>Pfeiltasten</p></td>
</tr>
<tr class="even">
<td><p>Erweitern des ausgewählten Knotens in der Struktur</p></td>
<td><p>+Schlüssel</p></td>
</tr>
<tr class="odd">
<td><p>Reduzieren des ausgewählten Knotens in der Struktur</p></td>
<td><p>-Schlüssel</p></td>
</tr>
<tr class="even">
<td><p>Zugreifen auf die Menüleiste</p></td>
<td><p>ALT-TASTE</p></td>
</tr>
<tr class="odd">
<td><p>Zugreifen auf einen Menüleistenbefehl</p></td>
<td><p>ALT-TASTE + der im Menü unterstrichene Buchstabe</p></td>
</tr>
<tr class="even">
<td><p>Auswählen der Dropdownliste im Zertifikat-Assistenten</p></td>
<td><p>Tab</p></td>
</tr>
<tr class="odd">
<td><p>Öffnen der Dropdownliste im Zertifikat-Assistenten</p></td>
<td><p>STRG + LEERTASTE</p></td>
</tr>
<tr class="even">
<td><p>Markieren eines Elements in der Dropdownliste im Zertifikat-Assistenten</p></td>
<td><p>TAB-TASTE und dann STRG+Pfeiltasten, um zwischen Elementen zu wechseln</p></td>
</tr>
<tr class="odd">
<td><p>Auswählen oder Löschen eines Elements in der Dropdownliste im Zertifikat-Assistenten</p></td>
<td><p>STRG + LEERTASTE</p></td>
</tr>
</tbody>
</table>


</div>

<span id="BKMK_AltText"></span>

<div>

## <a name="alternate-text-for-figures"></a>Alternativtext für Abbildungen

Jede Figur in lync Server 2013 Hilfe, einschließlich Screenshots, Diagrammen, Flussdiagrammen und anderen Abbildungen, weist einen alternativen Text auf. Benutzer, die Schwierigkeiten bei der Anzeige von Abbildungen haben, können den Cursor über der Abbildung positionieren und den Alternativtext lesen. Der Alternativtext beschreibt den Inhalt der Abbildung.

</div>

<span id="BKMK_AccessMS"></span>

<div>

## <a name="accessibility-products-and-services-from-microsoft"></a>Barrierefreiheitsprodukte und -dienste von Microsoft

Die folgenden Abschnitte enthalten Informationen zu den Features, Produkten und Diensten, die Windows für Personen mit Behinderungen leichter zugänglich machen.

<div>


> [!NOTE]  
> Die Informationen in diesem Abschnitt gelten nur für Benutzer, die Microsoft-Produkte in den USA lizenzpflichtig nutzen. Wenn Sie dieses Produkt außerhalb der Vereinigten Staaten erworben haben, können Sie die im Lieferumfang Ihres Softwarepakets enthaltene subsidiäre Informationskarte oder die Microsoft <A href="https://go.microsoft.com/fwlink/p/?linkid=18139">https://go.microsoft.com/fwlink/p/?linkId=18139</A> Accessibility-Website unter für eine Liste der Telefonnummern und Adressen für Microsoft-Supportdienste verwenden. Erfragen Sie bei Ihrer Niederlassung vor Ort, ob die in diesem Abschnitt beschriebenen Produkte und Dienste in Ihrer Region verfügbar sind. Weitere Informationen zu den in Microsoft-Produkten enthaltenen Barrierefreiheitsfunktionen finden Sie auf der Website für Barrierefreiheit in Microsoft-Produkte.



</div>

<div>

## <a name="accessibility-features-of-windows"></a>Barrierefreiheitsfeatures von Windows

Das Windows-Betriebssystem bietet zahlreiche integrierte Barrierefreiheitsfunktionen, die für Personen hilfreich sind, die eine Tastatur oder eine Maus nur mit Schwierigkeiten bedienen können, blind oder sehbehindert sind oder gehörlos oder hörgeschädigt sind. Diese Funktionen werden beim Setup installiert. Ausführliche Informationen zu diesen Features finden Sie unter Windows-Hilfe oder Microsoft [https://go.microsoft.com/fwlink/p/?linkId=18139](https://go.microsoft.com/fwlink/p/?linkid=18139)Accessibility.

  - **﻿Kostenlose Schritt-für-Schritt-Tutorials**   Microsoft bietet eine Reihe Schritt-für-Schritt-Anleitungen, in denen detaillierte Verfahren zum Anpassen der Barrierefreiheitsoptionen und Einstellungen auf dem Computer bereitgestellt werden. Diese Informationen werden parallel präsentiert, sodass Sie die Verwendung der Maus, der Tastatur oder die kombinierte Verwendung beider Eingabegeräte erlernen können.
    
    Eine Schritt-für-Schritt-Anleitung für Microsoft-Produkte finden Sie unter Microsoft [https://go.microsoft.com/fwlink/p/?linkId=18139](https://go.microsoft.com/fwlink/p/?linkid=18139)Accessibility unter.

  - **Hilfstechnologieprodukte für Windows**   eine Vielzahl von Hilfstechnologieprodukte stehen zur Verfügung, um die Verwendung von Computern für Personen mit Behinderungen zu verbessern. Sie können einen Katalog unterstützter Technologie Produkte Durchsuchen, die unter Windows auf der Microsoft Accessibility-Website [https://go.microsoft.com/fwlink/p/?linkId=18139](https://go.microsoft.com/fwlink/p/?linkid=18139)unter ausgeführt werden.
    
    Wenn Sie Hilfstechnologie verwenden, informieren Sie sich bei Ihrem Hilfstechnologieanbieter über mögliche Kompatibilitätsprobleme, bevor Sie Ihre Software oder Hardware aktualisieren.

</div>

<div>

## <a name="documentation-in-alternative-formats"></a>Dokumentation in alternativen Formaten

Falls Sie Probleme beim Lesen oder Verwenden von gedruckten Dokumenten haben, können Sie sich die Dokumentation für viele Microsoft-Produkte in anderen Formaten besorgen, die den Zugriff für Personen mit Behinderungen erleichtern. Einen Index der barrierefreien Produktdokumentation finden Sie auf der Microsoft Accessibility-Website [https://go.microsoft.com/fwlink/p/?linkId=18139](https://go.microsoft.com/fwlink/p/?linkid=18139)unter.

Darüber hinaus können Sie weitere Microsoft-Publikationen von Recording for the Blind & Legasthenie, Inc (RFB\&D) erhalten. RFB\&D verteilt diese Dokumente an registrierte, berechtigte Mitglieder Ihres Verteilungs Diensts. Informationen zur Verfügbarkeit der Microsoft-Produktdokumentation und der Bücher von Microsoft Press erhalten Sie\&von RFB D.


<table>
<colgroup>
<col style="width: 100%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p>Aufzeichnung für blinde &amp; Legasthenie, Inc.</p>
<p>20 Roszel Road</p>
<p>Princeton, NJ 08540, USA</p>
<p>Telefonnummer, wenn Sie innerhalb der USA anrufen: (800) 221-4792</p>
<p>Website: Aufzeichnung für blinde &amp; Legasthenie unter<a href="http://www.rfbd.org/" class="uri">http://www.rfbd.org/</a></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="customer-service-for-people-with-disabilities"></a>Kundendienst für Personen mit Behinderungen

Microsoft möchte allen Kunden die bestmögliche Erfahrung bieten, einschließlich Personen mit Behinderungen. Wenn Sie Hilfe benötigen, wenden Sie sich an unser Support Team für Barrierefreiheit, das geschult wird, um Personen mit Behinderungen per Telefon oder e-Mail zu helfen.

[Wenden Sie sich an den Antwort Schreibtisch für Behinderungen.](https://support.microsoft.com/gp/contact-microsoft-accessibility)

Direkte Telefonleitung: 1-800-936-5900

TTY: 1-800-892-5234

Werktags: 5 Uhr -21.00 Uhr (Pacific Time)

Wochenenden: 6.00 Uhr -15.00 Uhr (Pacific Time)

</div>

<div>

## <a name="customer-service-for-people-with-hearing-impairments"></a>Kundenservice für Personen mit Hörschädigungen

Wenn Sie taub oder hörgeschädigt sind, können Sie über den Texttelefondienst (TTY/TDD) auf alle Produkt- und Kundendienste von Microsoft zugreifen:

  - Kundendienst und -support stellt das Microsoft Sales Information Center unter der Rufnummer (800) 892-5234 montags bis freitags von 06:30 bis 17:30 Uhr (Pacific Time), außer an Feiertagen, zur Verfügung.

  - Technische Unterstützung in den USA bietet der Produktsupport von Microsoft, den Sie unter der Rufnummer (800) 892-5234 montags bis freitags von 06:00 bis 18:00 Uhr (Pacific Time) erreichen, außer an Feiertagen. In Kanada ist die Rufnummer (905) 568-9641 montags bis freitags von 08:00 bis 20:00 Uhr (Eastern Standard Time) erreichbar, außer an Feiertagen.

Der Microsoft-Produktsupport unterliegt den Preisen und Bedingungen, die zum Zeitpunkt der Inanspruchnahme des Diensts gelten. Ausführliche Informationen finden Sie unter Microsoft- [https://go.microsoft.com/fwlink/p/?linkId=18142](https://go.microsoft.com/fwlink/p/?linkid=18142)Support unter.

</div>

</div>

<div>

## <a name="for-more-information"></a>Weitere Informationen

Ausführliche Informationen dazu, wie barrierefreie Technologien für Computer das Leben von Menschen mit Behinderungen verbessern können, finden [https://go.microsoft.com/fwlink/p/?linkId=18139](https://go.microsoft.com/fwlink/p/?linkid=18139)Sie unter Microsoft Accessibility.

</div>

</div>

<span> </span>

</div>

</div>

</div>

