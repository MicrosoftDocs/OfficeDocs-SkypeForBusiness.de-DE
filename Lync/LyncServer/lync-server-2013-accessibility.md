---
title: 'Lync Server 2013: Barrierefreiheit'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Accessibility for people with disabilities
ms:assetid: 29c35a47-2513-425c-8b6b-250786573171
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204754(v=OCS.15)
ms:contentKeyID: 48183681
ms.date: 01/15/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 428270d63184ab991bbaeb5538240bdb50a5d0d0
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34839974"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="accessibility-in-lync-server-2013"></a>Barrierefreiheit in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2014-10-09_

Microsoft hat sich verpflichtet, seine Produkte und Dienste für alle Benutzer einfacher zu machen. In den folgenden Abschnitten finden Sie Informationen zu den Features, Produkten und Diensten, die dazu beitragen, lync Server 2013 für Personen mit Behinderungen barrierefreier zu gestalten.

<div>

## <a name="accessibility-features-of-lync-server-2013"></a>Barrierefreiheitsfeatures von lync Server 2013

Die folgenden Features in lync Server 2013 helfen, die Barrierefreiheit für Personen mit Behinderungen zu vereinfachen:

  - Tastenkombinationen

  - Alternativtext für Zahlen

Darüber hinaus können einige Barrierefreiheitsfeatures und Tools von Windows für lync Server-Benutzer mit Behinderungen vorteilhaft sein. Windows PowerShell-Größen-und Farbänderungen bieten Barrierefreiheitsoptionen bei Verwendung der lync Server-Verwaltungsshell. Ausführliche Informationen zu den Windows PowerShell-Barrierefreiheitsoptionen finden Sie unter "Barrierefreiheit in Windows PowerShell 2,0" in [http://go.microsoft.com/fwlink/p/?linkId=98964](http://go.microsoft.com/fwlink/p/?linkid=98964)der TechNet-Bibliothek unter.

</div>

<span id="BKMK_KeyboardShortcuts"></span>

<div>

## <a name="keyboard-shortcuts"></a>Tastenkombinationen

Sie können Tastenkombinationen verwenden, um mit der Benutzeroberfläche in den lync Server-Verwaltungstools und anderen Features zu interagieren.

Mithilfe von Tastenkombinationen können Sie die folgenden allgemeinen Aufgaben schnell ausführen.


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Zu diesem Zweck</th>
<th>Verwenden Sie diese Tastenkombination</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Wechseln zwischen Elementen auf der Benutzeroberfläche</p></td>
<td><p>Registerkarte</p></td>
</tr>
<tr class="even">
<td><p>Führen Sie die Aktion für das ausgewählte Element aus, beispielsweise " <strong>Alle anzeigen</strong>", " <strong>Alle ausblenden</strong>" oder einen Link öffnen.</p></td>
<td><p>Eingeben</p></td>
</tr>
<tr class="odd">
<td><p>Das ausgewählte Element in das nächste Element auf der Seite oder in einem Menü ändern</p></td>
<td><p>Registerkarte</p></td>
</tr>
<tr class="even">
<td><p>Das ausgewählte Element in das vorherige Element auf der Seite ändern.</p></td>
<td><p>UMSCHALT + TAB</p></td>
</tr>
<tr class="odd">
<td><p>Ändern des ausgewählten Elements auf der Seite oder im Menü nach oben, unten, Links oder rechts</p></td>
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
<td><p>Öffnen Sie die Menüleiste.</p></td>
<td><p>Alt</p></td>
</tr>
<tr class="odd">
<td><p>Zugreifen auf einen Menüleisten Befehl</p></td>
<td><p>ALT + Buchstabe im Kontextmenü unterstrichen.</p></td>
</tr>
<tr class="even">
<td><p>Wählen Sie im Zertifikat-Assistenten die Dropdownliste aus.</p></td>
<td><p>Registerkarte</p></td>
</tr>
<tr class="odd">
<td><p>Öffnen Sie die Dropdownliste im Zertifikat-Assistenten.</p></td>
<td><p>STRG + LEERTASTE</p></td>
</tr>
<tr class="even">
<td><p>Hervorheben eines Elements in der Dropdownliste im Zertifikat-Assistenten</p></td>
<td><p>Tab und dann STRG + Pfeiltasten, um zwischen den Elementen zu wechseln.</p></td>
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

## <a name="alternate-text-for-figures"></a>Alternativtext für Zahlen

Jede Abbildung in der Hilfe zu lync Server 2013, einschließlich Screenshots, Diagrammen, Flussdiagrammen und anderen Abbildungen, weist einen alternativen Text auf. Benutzer, die Probleme beim Anzeigen von Zahlen haben, können den Cursor auf der Abbildung anhalten, um den Alternativtext zu lesen. Der Alternativtext beschreibt, was in der Abbildung gezeigt wird.

</div>

<span id="BKMK_AccessMS"></span>

<div>

## <a name="accessibility-products-and-services-from-microsoft"></a>Barrierefreiheits Produkte und-Dienste von Microsoft

In den folgenden Abschnitten werden Informationen zu den Features, Produkten und Diensten bereitgestellt, die Windows für Personen mit Behinderungen barrierefreier machen.

<div>


> [!NOTE]  
> Die Informationen in diesem Abschnitt gelten nur für Benutzer, die Microsoft-Produkte in den Vereinigten Staaten lizenzieren. Wenn Sie dieses Produkt außerhalb der Vereinigten Staaten erworben haben, können Sie die im Lieferumfang Ihres Softwarepakets enthaltene Zusatz Informationskarte verwenden oder die Microsoft <A href="http://go.microsoft.com/fwlink/p/?linkid=18139">http://go.microsoft.com/fwlink/p/?linkId=18139</A> -Website für Barrierefreiheit besuchen, um eine Liste der Telefonnummern und Adressen für den Microsoft-Support zu erhalten. Services. Sie können sich an Ihre Niederlassung wenden, um herauszufinden, ob die in diesem Abschnitt beschriebenen Arten von Produkten und Dienstleistungen in Ihrem Gebiet zur Verfügung stehen. Weitere Informationen zu den Barrierefreiheitsfeatures, die in Microsoft-Produkten enthalten sind, finden Sie auf der Website Barrierefreiheit in Microsoft-Produkten.



</div>

<div>

## <a name="accessibility-features-of-windows"></a>Barrierefreiheitsfeatures von Windows

Das Windows-Betriebssystem verfügt über viele integrierte Barrierefreiheitsfeatures, die für Personen hilfreich sind, die Probleme bei der Eingabe oder Verwendung einer Maus haben, die blind sind oder sehbehindert sind oder die taub oder schwerhörig sind. Die Features werden während des Setups installiert. Details zu diesen Features finden Sie unter Windows-Hilfe oder Microsoft- [http://go.microsoft.com/fwlink/p/?linkId=18139](http://go.microsoft.com/fwlink/p/?linkid=18139)Barrierefreiheit unter.

  - **﻿Kostenlose Schritt-für-Schritt-Anleitungen**   Microsoft bietet eine Reihe von schrittweisen Lernprogrammen, in denen detaillierte Verfahren zum Anpassen der Barrierefreiheitsoptionen und-Einstellungen auf dem Computer bereitgestellt werden. Diese Informationen werden in einem nebeneinander angeordneten Format angezeigt, damit Sie erfahren, wie Sie die Maus, die Tastatur oder eine Kombination aus beidem verwenden können.
    
    Schritt-für-Schritt-Anleitungen für Microsoft-Produkte finden Sie unter Barrierefreiheit [http://go.microsoft.com/fwlink/p/?linkId=18139](http://go.microsoft.com/fwlink/p/?linkid=18139)in Microsoft.

  - **Hilfstechnologieprodukte für Windows**   eine große Auswahl an Hilfstechnologieprodukte steht zur Verfügung, um die Verwendung von Computern für Personen mit Behinderungen zu erleichtern. Sie können einen Katalog mit Hilfstechnologieprodukte durchsuchen, die unter Windows auf der Microsoft [http://go.microsoft.com/fwlink/p/?linkId=18139](http://go.microsoft.com/fwlink/p/?linkid=18139)-Website für Barrierefreiheit ausgeführt werden.
    
    Wenn Sie Hilfstechnologien verwenden, wenden Sie sich an Ihren Anbieter für Hilfstechnologien, bevor Sie Ihr Software-oder Hardware-Upgrade durchführen, um mögliche Kompatibilitätsprobleme zu überprüfen.

</div>

<div>

## <a name="documentation-in-alternative-formats"></a>Dokumentation in alternativen Formaten

Wenn Sie Probleme beim Lesen oder Umgang mit gedruckten Materialien haben, können Sie die Dokumentation für viele Microsoft-Produkte in barrierefreieren Formaten abrufen. Einen Index der barrierefreien Produktdokumentation finden Sie auf der Microsoft Accessibility-Website [http://go.microsoft.com/fwlink/p/?linkId=18139](http://go.microsoft.com/fwlink/p/?linkid=18139)unter.

Darüber hinaus können Sie weitere Microsoft-Publikationen aus der Aufzeichnung für Blind #a0 Legasthenie, Inc (RFB\&D) abrufen. RFB\&D verteilt diese Dokumente an registrierte, berechtigte Mitglieder Ihres Verteilungs Diensts. Informationen zur Verfügbarkeit der Microsoft-Produktdokumentation und Bücher von Microsoft Press erhalten Sie von\&RFB D.


<table>
<colgroup>
<col style="width: 100%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p>Aufzeichnung für blinde &amp; Legasthenie, Inc.</p>
<p>20 Roszel Road</p>
<p>Princeton, NJ 08540</p>
<p>Telefonnummer innerhalb der Vereinigten Staaten: (800) 221-4792</p>
<p>Website: Aufzeichnung für blinde &amp; Legasthenie unter<a href="http://www.rfbd.org/" class="uri">http://www.rfbd.org/</a></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="customer-service-for-people-with-disabilities"></a>Kundendienst für Personen mit Behinderungen

Microsoft möchte allen unseren Kunden, auch Menschen mit Behinderungen, die bestmögliche Erfahrung bieten. Wenn Sie Hilfe benötigen, wenden Sie sich an das Support Team für Barrierefreiheit, das geschult ist, um Personen mit Behinderungen per Telefon oder e-Mail zu helfen.

[Wenden Sie sich an den answer Desk für Behinderungen](http://support.microsoft.com/gp/contact-microsoft-accessibility)

Direktwahltelefon: 1-800-936-5900

TTY: 1-800-892-5234

Werktags: 5 Uhr -21.00 Uhr (Pazifik Zeit)

Wochenenden: 6.00 Uhr -15.00 Uhr (Pazifik Zeit)

</div>

<div>

## <a name="customer-service-for-people-with-hearing-impairments"></a>Kundenservice für Personen mit Hörschädigungen

Wenn Sie gehörlos oder schwerhörig sind, ist der vollständige Zugriff auf Microsoft-Produkte und-Kundendienste über einen Text Telephone-Service (TTY/TDD) verfügbar:

  - Wenden Sie sich für den Kundendienst an das Microsoft Sales Information Center unter (800) 892-5234 zwischen 6:30 Uhr. und 5:30 Uhr Pazifik Zeit, Montag bis Freitag, ohne Feiertage.

  - Wenden Sie sich für technische Hilfe in den Vereinigten Staaten an den Microsoft-Produkt Support unter (800) 892-5234 zwischen 6:00 Uhr. und 6:00 Uhr Pazifik Zeit, Montag bis Freitag, ohne Feiertage. In Kanada: Wählen Sie (905) 568-9641 zwischen 8:00 Uhr und 8:00 Uhr Eastern Time, Montag bis Freitag, ohne Feiertage.

Die Microsoft-Support Dienste unterliegen den Preisen, Bedingungen und Konditionen, die zum Zeitpunkt der Nutzung des Diensts gelten. Ausführliche Informationen finden Sie unter Microsoft [http://go.microsoft.com/fwlink/p/?linkId=18142](http://go.microsoft.com/fwlink/p/?linkid=18142)-Support unter.

</div>

</div>

<div>

## <a name="for-more-information"></a>Weitere Informationen

Details dazu, wie die barrierefreie Technologie für Computer hilft, das Leben von Menschen mit Behinderungen zu verbessern [http://go.microsoft.com/fwlink/p/?linkId=18139](http://go.microsoft.com/fwlink/p/?linkid=18139), finden Sie unter Barrierefreiheit in Microsoft.

</div>

</div>

<span> </span>

</div>

</div>

</div>

