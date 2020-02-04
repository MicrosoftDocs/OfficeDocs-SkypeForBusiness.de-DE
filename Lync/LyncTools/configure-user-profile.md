---
title: Benutzerprofil konfigurieren
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Configure User Profile
ms:assetid: 52713245-e502-4539-a238-66ff1aca26b1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945594(v=OCS.15)
ms:contentKeyID: 51541419
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a2441fe97bb57ffdf0f6200f1201e192bfc6bf14
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41727705"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-user-profile"></a>Benutzerprofil konfigurieren

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2018-10-11_

Die im lync Server 2013-Tool für Stress und Leistung enthaltenen Tools ermöglichen es Ihnen, Testbenutzerkonten zu erstellen und zu konfigurieren, die Sie zum Ausführen von Auslastungssimulationen verwenden können. Verwenden Sie das Benutzer Erstellungs Tool von lync Server 2013, um die Benutzer zu erstellen. (Weitere Informationen finden Sie unter [Erstellen von Benutzern und Kontakten](create-users-and-contacts.md).) Nachdem Benutzer erstellt wurden, konfigurieren Sie die Benutzerprofile mithilfe des lync Server 2013 Load Configuration-Tools.

<div>

## <a name="running-the-lync-server-2013-load-configuration-tool"></a>Ausführen des lync Server 2013 Load Configuration Tools

Wenn Sie Benutzerprofile konfigurieren möchten, führen Sie das lync Server 2013 Load Configuration Tool (UserProfileGenerator. exe) aus, und füllen Sie die einzelnen Registerkarten aus. UserProfileGenerator. exe generiert ein Verzeichnis für jeden Clientcomputer, den Sie zum Ausführen der Simulation benötigen. Jedes Clientverzeichnis enthält auch ein Skript zum Starten aller Instanzen des lync Server 2013-Stress-und-Leistungstools (LyncPerfTool. exe).

<div>


> [!IMPORTANT]  
> Die in UserProfileGenerator angegebenen benutzerspezifischen Werte müssen mit den Werten übereinstimmen, die im lync Server 2013-Benutzer Erstellungs Tool (UserProvisioningTool) für den Pool angegeben sind.



</div>

Füllen Sie die Felder auf jeder Registerkarte des lync Server 2013 Load Configuration-Tools aus, wie in den folgenden Abschnitten beschrieben.

<div>

## <a name="common-configuration"></a>Allgemeine Konfiguration

Die folgende Abbildung zeigt die Registerkarte " **Allgemeine Konfiguration** " im lync Server 2013 Load Configuration Tool. Füllen Sie die Felder auf der Registerkarte **Allgemeine Konfiguration** aus, wie in den folgenden Schritten beschrieben.

![Registerkarte "Allgemeine Konfiguration"](images/JJ945594.c68dcc8f-10f2-499e-95a2-fccbcc206c2f(OCS.15).jpg "Registerkarte "Allgemeine Konfiguration"")

1.  Geben Sie unter **Anzahl der verfügbaren**Computer die Anzahl der Computer ein, die Sie zum Ausführen von LyncPerfTool. exe verwenden möchten, oder klicken Sie darauf. Wir empfehlen, dass Sie über einen Computer für alle 4.500-Benutzer verfügen, die Sie simulieren werden. Diese Nummer kann variieren, wenn Sie den Ladebereich verringern oder nur einen Teil der verfügbaren Funktionen verwenden. (Die Ladestufen werden auf der Registerkarte **Allgemeine Szenarien** eingestellt.)

2.  Geben Sie in **Prefix für Benutzernamen**das Präfix für den Benutzernamen der Benutzer ein. Um sich anzumelden, wird der Uniform Resource Identifier (URI) wie folgt\[angegeben: UserPrefix User Start Index... (Anzahl der Benutzer-1) \]@User Domäne.

3.  Geben Sie unter **Kennwort für alle Benutzer**das Kennwort ein, das zum Erstellen der Benutzer verwendet wurde. Wenn Sie dieses Feld leer lassen, wird der Benutzername als Kennwort verwendet.

4.  Klicken Sie im **Start Index des Benutzers**auf den Index des ersten Benutzers, den Sie konfigurieren möchten, oder geben Sie ihn ein. Sie können verschiedene Bereiche für verschiedene Typen oder lade Ebenen konfigurieren, aber Sie müssen UserProfileGenerator. exe einmal pro Bereich ausführen, den Sie konfigurieren möchten.

5.  Klicken Sie unter **Anzahl der Benutzer**auf die Gesamtzahl der Benutzer, die Sie konfigurieren möchten, oder geben Sie Sie ein.

6.  Geben Sie in **Benutzerdomäne**die Domäne ein, die für den SIP-URI verwendet wird. Diese wird verwendet, um den SIP-URI jedes Benutzers zu erstellen, der sich am lync Server 2013-Front-End-Server oder Standard Edition-Server anmeldet. Sie kann sich von der Kontodomäne unterscheiden.

7.  Geben Sie in **Kontodomäne**die Domänenanmeldung für Active Directory-Domänendienste ein.

8.  Geben Sie die maximale Anzahl von gleichzeitigen Endpunkten in **Anmeldung pro Sekunde (pro Instanz)** ein, für die Sie das Tool an allen Endpunkten/Benutzern protokollieren möchten. Die empfohlene Gebühr ist \<= 2 pro Sekunde/Standard SKU Fe.

9.  Geben Sie in **Access-Proxy oder Pool-FQDN**den vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) des Servers ein, mit dem die Clients eine Verbindung herstellen möchten. Wenn sich die Benutzer extern anmelden, geben Sie den Zugriffsproxy an. Wenn die Benutzer intern sind, geben Sie den FQDN Ihres Pools oder Standard Edition-Servers an.

10. Klicken oder geben Sie in **Port**den Port ein, den Benutzer für SIP verwenden sollen (der Standardwert ist 5061).

Geben Sie für externe Netzwerk Server Einstellungen den **Zugriffs Proxy oder den Pool-FQDN** und den **Port**an. Diese Einstellungen werden nur für die Auslastungssimulation externer Endpunkte verwendet.

</div>

<div>

## <a name="general-scenarios"></a>Allgemeine Szenarien

Die Registerkarte " **Allgemeine Szenarien** " im lync Server 2013 Load Configuration Tool ist in der folgenden Abbildung dargestellt.

Konfigurieren Sie die Auslastungsstufen und Parameter für die einzelnen allgemeinen Szenarien, die Sie ausführen möchten, oder lassen Sie deaktiviert.

![Registerkarte "allgemeine Szenarien"](images/JJ945594.4f046d39-b532-4baf-99a6-c89d1d6d1fcc(OCS.15).jpg "Registerkarte "allgemeine Szenarien"")

1.  Geben Sie in **Instant Messaging**, das Peer-to-Peer und Konferenzen umfasst, den entsprechenden Wert für die Auslastungsstufe an.
    
    <div>
    

    > [!NOTE]  
    > Die Werte für die Auslastungsstufe für alle Felder (mit Ausnahme von Standort Informationsdiensten) sind <STRONG>deaktiviert</STRONG>, <STRONG>gering</STRONG>, <STRONG>Mittel</STRONG>, <STRONG>hoch</STRONG>und <STRONG>Benutzerdefiniert</STRONG>. Wenn "Low", "Mittel", "hoch" oder "Benutzerdefiniert" ausgewählt ist, werden für jede Modalität und jeden Clientkonfigurationen generiert. "Hoch" führt zu der maximalen unterstützten Last, die für den Server generiert wird, das Medium entspricht 60 Prozent der Last, und "Low" entspricht 30 Prozent der Auslastung.

    
    </div>

2.  Geben Sie in **Audiokonferenzen**, bei denen es sich nur um Audiokonferenzen handelt, den entsprechenden Wert für Load Level an. Peer-zu-Peer-Anrufe werden im Abschnitt VoIP-Szenarien weiter unten in diesem Thema behandelt. Um MultiView zu aktivieren, öffnen Sie die Registerkarte **erweitert** für diese Modalität.

3.  Geben Sie in **Anwendungsfreigabe**den entsprechenden Wert für Load Level an.

4.  Geben Sie in der **Datenzusammenarbeit**, die Datenkonferenzen umfasst, den entsprechenden Wert für Load Level an.

5.  Geben Sie in **Expansion der Verteilerliste**den entsprechenden Wert für Load Level an. Sie müssen auch auf die Schaltfläche **erweitert** klicken und dann die Felder mit den gleichen Werten ausfüllen, die Sie auf der Registerkarte **Verteilerliste** des lync Server-Benutzer Erstellungstools (UserProvisioningTool. exe) konfiguriert haben. Details zu diesen Feldern finden Sie unter [Erstellen von Benutzern und Kontakten](create-users-and-contacts.md) .

6.  Geben Sie in der **Adressbuch-Webabfrage**, bei der es sich um den Adressbuch-Suchdienst (nicht den Adressbuchdatei-Download) handelt, den entsprechenden Wert für Load Level an. Um Adressbuch Downloads zu aktivieren, klicken Sie auf die entsprechende Schaltfläche **erweitert** , und legen Sie **EnableABSDownload** auf true fest.

7.  Geben Sie im **Reaktionsgruppendienst**den entsprechenden Wert für Load Level an. Sie müssen auch auf die entsprechende Schaltfläche **erweitert** klicken und dann die URIs der Reaktionsgruppen angeben, die Sie bereits beim Bereitstellen von Reaktionsgruppen-Service-Agents erstellt haben. Sie müssen mindestens eine Reaktionsgruppe angeben. Verwenden Sie Semikolons, um mehrere Antwortgruppen voneinander zu trennen. Aktualisieren Sie RGSUriSuffixStartIndex und RGSUriSuffixEndIndex auf die tatsächlichen Werte.

8.  Wählen Sie in **Standort Informationsdienste**den geeigneten Wert für Auslastungsgrad aus. Die Auslastungsstufe für Standort Informationsdienste muss **aktiviert** oder **deaktiviert**sein.

<div>


> [!NOTE]  
> In jedem der Szenarien befindet sich neben der Schaltfläche " <STRONG>erweitert</STRONG> " und eine Reihe von Kontrollkästchen, die Variationen der Szenarien ermöglichen. <STRONG>Ad-hoc-</STRONG> Mittel zur Simulation von Konferenzen, die während der gesamten Stunde erstellt werden. <STRONG>Große conf</STRONG> bedeutet, dass große Konferenzszenarien simuliert werden. <STRONG>Externe</STRONG> Mittel, um auch externe Benutzer zu simulieren.<BR>Diese Schaltflächen und Kontrollkästchen ermöglichen den Zugriff auf Werte, die für jedes Szenario spezifisch sind, das das Verhalten des lync Server 2013-Stress-und-Leistungstools (LyncPerfTool) ändert und die Anpassung möglich macht. Bei jedem Szenario auf der Registerkarte <STRONG>Allgemeine Szenarien</STRONG> (mit Ausnahme von Standort Informationsdiensten) wird die Konversations Rate mithilfe des entsprechenden Felds im Dialogfeld <STRONG>erweitert</STRONG> berechnet, wenn der Wert der Auslastungsstufe <STRONG>Benutzerdefiniert</STRONG>ist. Der Feldname unterscheidet sich je nach Szenario, aber die Feld Beschreibung gibt an, "Hinweis: Diese Nummer wird nur verwendet, wenn im Dropdownmenü" Benutzerdefiniert "ausgewählt ist. Im allgemeinen ändern die Werte " <STRONG>hoch</STRONG>", " <STRONG>Mittel</STRONG>" und " <STRONG>tief</STRONG> " die Konversations Raten pro Modalwert entsprechend dem Benutzermodell, bei dem es sich um ein Gleichgewicht aller Szenarien handelt. Wenn es erforderlich ist, den Auslastungsgrad pro Modalwert aufgrund einer unterschiedlichen erwarteten Nutzung zu ändern, empfehlen wir die Verwendung einer <STRONG>benutzerdefinierten</STRONG> Konversations Gebühr.<BR>



</div>

</div>

<div>

## <a name="voice-scenarios"></a>Sprachszenarien

Die Registerkarte " **VoIP-Szenarien** " im lync Server 2013 Load Configuration Tool ist in der folgenden Abbildung dargestellt.

Verwenden Sie die Registerkarte **VoIP-Szenarien** , um alle sprachbezogenen Szenarien zu konfigurieren.

![Registerkarte "Sprachszenarien"](images/JJ945594.28edf664-da59-40b0-9a0e-196f01e9ca86(OCS.15).jpg "Registerkarte "Sprachszenarien"")

1.  Klicken Sie in **VoIP**auf die Schaltfläche **erweitert** , und geben Sie dann Werte für die Felder **PhoneAreaCode** und **LocationProfile** (Wählplan) ein. Außerdem müssen Sie einen Wert für **Load Level**angeben. Wenn Load Level für **VoIP** und **UC/PSTN-Gateway** aktiviert ist, wird immer ein öffentliches Switched Telephone Network (PSTN) zur Unified Communications (UC)-Konfigurationsdatei generiert, die externe Anrufe simuliert.

2.  Geben Sie in **UC/PSTN-Gateway**einen Wert für Load Level an. Wenn Sie eine andere Ladeebene als **deaktiviert**auswählen, müssen Sie einen Wert für die **PSTN-Vorwahl** angeben, indem Sie unter Mediation Server und PSTN auf die Schaltfläche **Hinzufügen** klicken. Stellen Sie sicher, dass für diese Ortsvorwahl eine Route konfiguriert ist.
    
    <div>
    

    > [!NOTE]  
    > Sie können entweder die lync Server-Systemsteuerung oder die lync Server-Verwaltungsshell verwenden, um die Konfiguration der VoIP-Route zu überprüfen.

    
    </div>

3.  Geben Sie in **Conferencing Attendant**einen Wert für Load Level an. Wenn Sie einen Ladebereich (außer **disabled**) auswählen, wird das Feld **Telefonnummer** aktiviert. Geben Sie die Telefonnummer der automatischen Telefonzentrale ein, die Sie verwenden möchten. Klicken Sie auch auf die Schaltfläche **erweitert** , und geben Sie dann einen Wert für das **LocationProfile** -Feld ein.

4.  Geben Sie im Dienst für das **Parken von Anrufen**den entsprechenden Wert für **Auslastungsgrad**an.

5.  In **Mediation Server und PSTN**müssen Sie für jeden Vermittlungsserver, den Sie verwenden möchten, über einen separaten PSTN-Simulator verfügen. Nachdem Sie festgestellt haben, welchen Client Sie als Simulator verwenden möchten, müssen Sie Ihren Vermittlungs Server so konfigurieren, dass Anrufe an diesen Computer auf dem von Ihnen konfigurierten PSTN-Simulator-Port weitergeleitet werden. Klicken Sie auf **Hinzufügen** , um den Wert für den Vermittlungs Server zu konfigurieren.

<div>


> [!NOTE]  
> In jedem der Szenarien befindet sich daneben eine Schaltfläche " <STRONG>erweitert</STRONG> ". Diese Schaltflächen ermöglichen den Zugriff auf Werte, die für jedes Szenario spezifisch sind, das das Verhalten des lync Server 2013 Stress and Performance Tool (LyncPerfTool) ändert und die Anpassung ermöglicht. Bei jedem Szenario auf der Registerkarte <STRONG>VoIP-Szenarien</STRONG> , wenn der Wert der <STRONG>Auslastungsstufe</STRONG> <STRONG>Benutzerdefiniert</STRONG>ist, wird die Konversations Rate mithilfe des entsprechenden Felds im Dialogfeld <STRONG>erweitert</STRONG> berechnet. Der Feldname unterscheidet sich je nach Szenario, aber die Feld Beschreibung gibt an, "Hinweis: Diese Nummer wird nur verwendet, wenn im Dropdownmenü" Benutzerdefiniert "ausgewählt ist.



</div>

</div>

<div>

## <a name="reach"></a>Erreichen

REACH ist eine neue Erfahrung in lync Server 2013, die Konferenzszenarien über den Unified Communications Web API-Server (UCWA) unterstützt, der auf dem Front-End-Server installiert ist. Die Registerkarte " **REACH** " des lync Server 2013 Load Configuration-Tools ist in der folgenden Abbildung dargestellt.

Verwenden Sie die Registerkarte **REACH** , um alle REACH-bezogenen Szenarien zu konfigurieren.

![Registerkarte "REACH"](images/JJ945594.65ccf6de-0e8d-47ba-93f3-9dcb39d3fd62(OCS.15).jpg "Registerkarte "REACH"")

1.  Klicken Sie auf die Schaltfläche **erweitert** neben **Allgemeine Einstellungen für REACH**. Legen Sie das Feld **UcwaTargetServerUrl** auf den Director Pool Virtual IP (VIP) oder den Front-End-Pool VIP.

2.  Wählen Sie in **Anwendungsfreigabe**, **Datenzusammenarbeit**und **Chat**den entsprechenden Wert für **Load Level**aus.

<div>


> [!NOTE]  
> In jedem der Szenarien befindet sich daneben eine Schaltfläche " <STRONG>erweitert</STRONG> ". Diese Schaltflächen ermöglichen den Zugriff auf Werte, die für jedes Szenario spezifisch sind, das das Verhalten des lync Server 2013 Stress and Performance Tool (LyncPerfTool) ändert und die Anpassung ermöglicht. Bei jedem der REACH-Szenarien wird, wenn die <STRONG>Auslastungsstufe</STRONG> <STRONG>Benutzerdefiniert</STRONG>ist, der im Feld <STRONG>ConversationsPerHour</STRONG> angegebene Wert anstelle des Standardwerts verwendet.



</div>

Verwenden Sie die Registerkarte **Mobilität** , um alle mobilitätsbezogenen Szenarien zu konfigurieren.

![Reiter Mobilität.](images/JJ945594.4dd8f3e0-921c-48a5-8b23-2a0330d3c334(OCS.15).jpg "Reiter Mobilität.")

1.  Klicken Sie auf die Schaltfläche **erweitert** neben **Mobilität (UCWA)**. Legen Sie das Feld **UcwaTargetServerUrl** auf den Director Pool Virtual IP (VIP) oder den Front-End-Pool VIP.

2.  Wählen Sie in **Anwesenheits-\\und P2P-Instant Messaging-Audio**den entsprechenden Wert für **Load Level** aus, um die Mobilitäts Szenario-Simulation zu aktivieren.

<div>


> [!NOTE]  
> In jedem der Szenarien befindet sich daneben eine Schaltfläche " <STRONG>erweitert</STRONG> ". Diese Schaltflächen ermöglichen den Zugriff auf Werte, die für jedes Szenario spezifisch sind, das das Verhalten des lync Server 2013 Stress and Performance Tool (LyncPerfTool) ändert und die Anpassung ermöglicht. Bei jedem der REACH-Szenarien wird, wenn die <STRONG>Auslastungsstufe</STRONG> <STRONG>Benutzerdefiniert</STRONG>ist, der im Feld <STRONG>ConversationsPerHour</STRONG> angegebene Wert anstelle des Standardwerts verwendet.



</div>

</div>

<div>

## <a name="summary"></a>Zusammenfassung

Die Registerkarte " **Zusammenfassung** " des lync Server 2013 Load Configuration-Tools ist in der folgenden Abbildung dargestellt.

![Registerkarte "Zusammenfassung"](images/JJ945594.c675e869-8ded-4195-8c2a-68d844fc96ad(OCS.15).jpg "Registerkarte "Zusammenfassung"")

Die Registerkarte " **Zusammenfassung** " gibt an, welche Benutzer für die einzelnen Szenarien verwendet werden sollen. Es ist möglich, Benutzernummern Bereiche manuell zu konfigurieren, indem Sie das Kontrollkästchen Benutzer **definierte Benutzerbereichs Generierung aktivieren** auswählen und dann in der Tabelle mit dem **Benutzerbereich** , den Sie anpassen möchten, auf das Szenario doppelklicken. Überprüfen (RunClient. bat) fügen Sie beim Starten eine Anmelde Verzögerung hinzu, um Verzögerungen in den generierten Batchdateien einzubeziehen, damit Sie dem Anmelde Satz entsprechen. Dies ist nützlich, um eine Serverüberlastung zu verhindern, wenn eine große Anzahl von Benutzern signiert wird. Klicken Sie auf **Dateien generieren**, und wählen Sie den Ordner aus, in dem Sie die Konfiguration generieren möchten. Wenn Ihre Dateien erfolgreich erstellt wurden, wird ein Dialogfeld angezeigt, das der folgenden Abbildung ähnelt.

![Bestätigung, dass Dateien erstellt wurden.](images/JJ945594.00dc1e92-bfba-48e7-9568-b97ad864491e(OCS.15).jpg "Bestätigung, dass Dateien erstellt wurden.")

</div>

</div>

<div>

## <a name="see-also"></a>Siehe auch


[Erstellen von Benutzern und Kontakten](create-users-and-contacts.md)  
</div>
</div>
<span></span>
</div>
</div>
</div>
