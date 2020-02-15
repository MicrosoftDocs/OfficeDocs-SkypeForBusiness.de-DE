---
title: Konfigurieren des Benutzerprofils
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
ms.openlocfilehash: 842a5ade3e0484d0b084f48ac75a2b13984706e5
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42049257"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-user-profile"></a>Konfigurieren des Benutzerprofils

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2018-10-11_

Mit den im lync Server 2013 Stress and Performance Tool-Paket enthaltenen Tools können Sie Testbenutzerkonten erstellen und konfigurieren, mit denen Sie Auslastungssimulationen ausführen können. Verwenden Sie das lync Server 2013 Benutzer Erstellungs Tool, um die Benutzer zu erstellen. (Weitere Informationen finden Sie unter [Create users and Contacts](create-users-and-contacts.md).) Nachdem Benutzer erstellt wurden, konfigurieren Sie die Benutzerprofile mithilfe des lync Server 2013 Tools zum Laden der Konfiguration.

<div>

## <a name="running-the-lync-server-2013-load-configuration-tool"></a>Ausführung des lync Server 2013 Lade Konfigurationstools

Zum Konfigurieren von Benutzerprofilen führen Sie das lync Server 2013 laden-Konfigurations Tool (UserProfileGenerator. exe) aus, und füllen Sie die einzelnen Registerkarten aus. UserProfileGenerator. exe generiert ein Verzeichnis für jeden Clientcomputer, den Sie zum Ausführen der Simulation benötigen. Jedes Clientverzeichnis enthält auch ein Skript zum Starten aller Instanzen des lync Server 2013 Stress and Performance Tool (LyncPerfTool. exe).

<div>


> [!IMPORTANT]  
> Die in UserProfileGenerator angegebenen benutzerspezifischen Werte müssen mit den Werten übereinstimmen, die im lync Server 2013-Benutzer Erstellungs Tool (UserProvisioningTool) für den Pool angegeben sind.



</div>

Füllen Sie die Felder auf jeder Registerkarte des lync Server 2013 Auslastungs Konfigurationstools aus, wie in den folgenden Abschnitten beschrieben.

<div>

## <a name="common-configuration"></a>Allgemeine Konfiguration

Die folgende Abbildung zeigt die Registerkarte " **Allgemeine Konfiguration** " des lync Server 2013 Tools zum Laden der Konfiguration. Füllen Sie die Felder auf der Registerkarte **Allgemeine Konfiguration** aus, wie in den folgenden Schritten beschrieben.

![Allgemeine Konfigurationsregisterkarte.](images/JJ945594.c68dcc8f-10f2-499e-95a2-fccbcc206c2f(OCS.15).jpg "Allgemeine Konfigurationsregisterkarte.")

1.  Geben Sie unter **Anzahl der verfügbaren**Computer die Anzahl von Computern ein, die Sie zum Ausführen von LyncPerfTool. exe verwenden möchten, oder klicken Sie darauf. Es wird empfohlen, dass Sie einen Computer für jeden 4.500-Benutzer haben, den Sie simulieren werden. Diese Nummer kann variieren, wenn Sie die Auslastungsstufe verringern oder wenn Sie nur eine Teilmenge der verfügbaren Features verwenden. (Auf der Registerkarte **Allgemeine Szenarien** werden Ladestufen festgelegt.)

2.  Geben Sie unter **Präfix für Benutzernamen**das Präfix für den Benutzernamen der Benutzer ein. Um sich anzumelden, wird der URI (Uniform Resource Identifier): UserPrefix\[User Start Index... (Anzahl der Benutzer-1) \]@User Domäne.

3.  Geben Sie unter **Kennwort für alle Benutzer**das Kennwort ein, das zum Erstellen der Benutzer verwendet wurde. Wenn Sie dieses Feld leer lassen, wird der Benutzername als Kennwort verwendet.

4.  Klicken Sie im **Start Index des Benutzers**auf oder geben Sie den Index des ersten Benutzers ein, der konfiguriert werden soll. Sie können verschiedene Bereiche für verschiedene Typen oder Last Ebenen konfigurieren, aber Sie müssen UserProfileGenerator. exe einmal pro Bereich ausführen, den Sie konfigurieren möchten.

5.  Klicken Sie unter **Anzahl der Benutzer**auf oder geben Sie die Gesamtzahl der Benutzer ein, die Sie konfigurieren möchten.

6.  Geben Sie in **Benutzerdomäne**die für den SIP-URI verwendete Domäne ein. Dies wird verwendet, um den SIP-URI jedes Benutzers zu erstellen, der sich am lync Server 2013 Front-End-Server oder Standard Edition-Server anmeldet. Es kann sich von der Kontodomäne unterscheiden.

7.  Geben Sie unter **Kontodomäne**die Active Directory-Domänendienste Domänenanmeldung ein.

8.  Geben Sie die maximale Anzahl gleichzeitiger Endpunkte in der **Anmeldung pro Sekunde (pro Instanz)** ein, für die das Tool sich in allen Endpunkten/Benutzern anmelden soll. Die empfohlene Rate beträgt \<= 2 pro Sekunde/Standard-SKU Fe.

9.  Geben Sie in **Zugriffs Proxy oder Pool-FQDN**den vollqualifizierten Domänennamen (FQDN) des Servers ein, mit dem die Clients eine Verbindung herstellen möchten. Wenn sich die Benutzer extern anmelden, geben Sie den Zugriffsproxy an. Wenn die Benutzer intern sind, geben Sie den FQDN des Pools oder Standard Edition-Server an.

10. Klicken oder geben Sie in **Port**den Port ein, den Benutzer für SIP verwenden sollen (der Standardwert lautet 5061).

Geben Sie für externe Netzwerk Server Einstellungen den **Zugriffs Proxy oder Pool-FQDN** und den **Port**an. Diese Einstellungen werden nur für die Auslastungssimulation externer Endpunkte verwendet.

</div>

<div>

## <a name="general-scenarios"></a>Allgemeine Szenarien

Die folgende Abbildung zeigt die Registerkarte **Allgemeine Szenarien** des lync Server 2013 Tools zum Laden der Konfiguration.

Konfigurieren Sie die Ladestufen und Parameter für jedes der allgemeinen Szenarien, die Sie ausführen möchten, oder lassen Sie die Option deaktiviert.

![Registerkarte Allgemeine Szenarien.](images/JJ945594.4f046d39-b532-4baf-99a6-c89d1d6d1fcc(OCS.15).jpg "Registerkarte Allgemeine Szenarien.")

1.  Geben Sie in **Instant Messaging**, das Peer-to-Peer und Konferenzen umfasst, den entsprechenden Wert für die Auslastungsstufe an.
    
    <div>
    

    > [!NOTE]  
    > Werte für die lastebene für alle Felder (außer Standort Informationsdienste) sind <STRONG>deaktiviert</STRONG>, <STRONG>niedrig</STRONG>, <STRONG>Mittel</STRONG>, <STRONG>hoch</STRONG>und <STRONG>Benutzerdefiniert</STRONG>. Wenn niedrig, Mittel, hoch oder Benutzerdefiniert ausgewählt ist, werden Konfigurationen für jede Modalität und jeden Client generiert. High bewirkt, dass die maximale unterstützte Last für den Server generiert wird, das Medium entspricht 60% der Last, und Low entspricht 30% der Last.

    
    </div>

2.  Geben Sie in **Audiokonferenzen**, bei denen es sich nur um Audiokonferenzen handelt, den entsprechenden Wert für die Auslastungsstufe an. Peer-zu-Peer-Anrufe werden weiter unten in diesem Thema im Abschnitt VoIP-Szenarien behandelt. Um MultiView zu aktivieren, öffnen Sie die Registerkarte **erweitert** für diese Modalität.

3.  Geben Sie in **Anwendungsfreigabe**den entsprechenden Wert für die Auslastungsstufe an.

4.  Geben Sie in **Datenzusammenarbeit**, einschließlich Datenkonferenzen, den entsprechenden Wert für die Auslastungsstufe an.

5.  Geben Sie in **Verteilerlistenerweiterung**den entsprechenden Wert für die Auslastungsstufe an. Sie müssen auch auf die Schaltfläche **erweitert** klicken und dann die Felder mit den gleichen Werten ausfüllen, die Sie auf der Registerkarte **Verteilerliste** des lync Server Benutzer Erstellungstools (UserProvisioningTool. exe) konfiguriert haben. Ausführliche Informationen zu diesen Feldern finden Sie unter [Create users and Contacts](create-users-and-contacts.md) .

6.  Geben Sie in der **Adressbuch-Webabfrage**, bei der es sich um den Adressbuch Suchdienst (nicht den Adressbuchdatei Download) handelt, den entsprechenden Wert für die Auslastungsstufe an. Klicken Sie zum Aktivieren der Adressbuch Downloads auf die entsprechende Schaltfläche **erweitert** , und legen Sie **EnableABSDownload** auf true fest.

7.  Geben Sie im **Reaktionsgruppendienst**den entsprechenden Wert für die Auslastungsstufe an. Sie müssen auch auf die entsprechende Schaltfläche **erweitert** klicken und dann die URIs der Reaktionsgruppen angeben, die Sie bereits erstellt haben, wenn Sie Reaktionsgruppen-Dienst-Agents zur Verfügung stellen. Sie müssen mindestens eine Reaktionsgruppe angeben. Verwenden Sie Semikolons, um mehrere Reaktionsgruppen voneinander zu trennen. Aktualisieren Sie RGSUriSuffixStartIndex und RGSUriSuffixEndIndex auf die tatsächlichen Werte.

8.  Wählen Sie unter **Standort Informationsdienste**den entsprechenden Wert für lastebene aus. Die Auslastungsstufe für Standort Informationsdienste muss **aktiviert** oder **deaktiviert**werden.

<div>


> [!NOTE]  
> In jedem der Szenarien befinden sich neben der Schaltfläche <STRONG>Erweiterte</STRONG> Schaltflächen und eine Reihe von Kontrollkästchen, die Variationen der Szenarien ermöglichen. <STRONG>Ad-hoc</STRONG> bedeutet, dass die Simulation von Konferenzen generiert wird, die die ganze Stunde hindurch erstellt werden. <STRONG>Large conf</STRONG> bedeutet, dass großes Konferenz Szenario simuliert wird. <STRONG>Externe</STRONG> Mittel, um auch externe Benutzer zu simulieren.<BR>Diese Schaltflächen und Kontrollkästchen ermöglichen den Zugriff auf die spezifischen Werte für jedes Szenario, das das Verhalten des lync Server 2013 Stress-und Leistungstools (LyncPerfTool) ändert und die Anpassung ermöglichen kann. Wenn der Wert der Auslastungsstufe <STRONG>Custom</STRONG>ist, wird für jedes Szenario auf der Registerkarte <STRONG>Allgemeine Szenarien</STRONG> (mit Ausnahme von Standort Informationsdiensten) die Konversations Rate mithilfe des entsprechenden Felds im Dialogfeld <STRONG>erweitert</STRONG> berechnet. Der Feldname unterscheidet sich je nach Szenario, aber die Feld Beschreibung gibt an, "Hinweis: Diese Nummer wird nur verwendet, wenn Benutzerdefiniert aus dem Dropdownmenü ausgewählt wird." Im allgemeinen ändern die Werte <STRONG>hoch</STRONG>, <STRONG>Mittel</STRONG>und <STRONG>niedrig</STRONG> die Gesprächs Raten pro Modalität entsprechend dem Benutzermodell, das eine Balance aller Szenarien darstellt. Wenn aufgrund eines Unterschieds in der erwarteten Nutzung die Auslastungsstufe pro Modalität geändert werden muss, wird die Verwendung einer <STRONG>benutzerdefinierten</STRONG> Unterhaltungs Rate empfohlen.<BR>



</div>

</div>

<div>

## <a name="voice-scenarios"></a>VoIP-Szenarien

In der folgenden Abbildung ist die Registerkarte **VoIP-Szenarien** des lync Server 2013 Tools zur Lasten Konfiguration dargestellt.

Verwenden Sie die Registerkarte **VoIP-Szenarien** , um alle VoIP-bezogenen Szenarien zu konfigurieren.

![Registerkarte VoIP-Szenarien.](images/JJ945594.28edf664-da59-40b0-9a0e-196f01e9ca86(OCS.15).jpg "Registerkarte VoIP-Szenarien.")

1.  Klicken Sie in **VoIP**auf die Schaltfläche **erweitert** , und geben Sie dann Werte für die Felder **PhoneAreaCode** und **LocationProfile** (Wählplan) an. Sie müssen auch einen Wert für die **Auslastungsstufe**angeben. Wenn die Auslastungsstufe für **VoIP** und **UC/PSTN-Gateway** aktiviert ist, wird immer ein öffentliches Telefonnetz (PSTN) zu Unified Communications (UC)-Konfigurationsdatei generiert, das externe Anrufe simuliert wird.

2.  Geben Sie in **UC/PSTN-Gateway**einen Wert für die Auslastungsstufe an. Wenn Sie eine andere lastebene als **deaktiviert**auswählen, müssen Sie einen Wert für die **PSTN-Vorwahl** angeben, indem Sie unter Vermittlungsserver und PSTN auf die Schaltfläche **Hinzufügen** klicken. Stellen Sie sicher, dass für diese Ortskennzahl eine Route konfiguriert ist.
    
    <div>
    

    > [!NOTE]  
    > Sie können entweder die lync Server-Systemsteuerung oder die lync Server-Verwaltungsshell verwenden, um die Konfiguration der VoIP-Route zu überprüfen.

    
    </div>

3.  Geben Sie in der **Konferenzzentrale**einen Wert für die Auslastungsstufe an. Wenn Sie eine lastebene (nicht **deaktiviert**) auswählen, wird das Feld **Telefonnummer** aktiviert. Geben Sie die Telefonnummer der automatischen Telefonzentrale ein, die Sie verwenden möchten. Klicken Sie außerdem auf die Schaltfläche **erweitert** , und geben Sie einen Wert für das Feld **LocationProfile** ein.

4.  Geben Sie im Bereich " **Parken von Anrufen**" den entsprechenden Wert für die **Auslastungsstufe**an.

5.  In **Vermittlungsserver und PSTN**müssen Sie für jede Vermittlungsserver, die Sie verwenden möchten, über einen separaten PSTN-Simulator verfügen. Nachdem Sie festgestellt haben, welcher Client als Simulator verwendet werden soll, müssen Sie Ihre Vermittlungsserver so konfigurieren, dass Anrufe an diesen Computer auf dem von Ihnen konfigurierten PSTN-Simulator-Port weitergeleitet werden. Klicken Sie auf **Hinzufügen** , um den Wert für die Vermittlungsserver zu konfigurieren.

<div>


> [!NOTE]  
> In jedem der Szenarien befindet sich daneben eine Schaltfläche " <STRONG>erweitert</STRONG> ". Diese Schaltflächen ermöglichen den Zugriff auf spezifische Werte für jedes Szenario, das das Verhalten des lync Server 2013 Stress and Performance Tool (LyncPerfTool) ändert und die Anpassung aktiviert. Wenn der Wert der <STRONG>Auslastungsstufe</STRONG> <STRONG>Custom</STRONG>ist, wird für jedes Szenario auf der Registerkarte <STRONG>VoIP-Szenarien</STRONG> die Konversations Rate mithilfe des entsprechenden Felds im Dialogfeld <STRONG>erweitert</STRONG> berechnet. Der Feldname unterscheidet sich je nach Szenario, aber die Feld Beschreibung gibt an, "Hinweis: Diese Nummer wird nur verwendet, wenn Benutzerdefiniert aus dem Dropdownmenü ausgewählt wird."



</div>

</div>

<div>

## <a name="reach"></a>Erreichen

REACH ist eine neue Erfahrung in lync Server 2013, die Konferenzszenarien über den Unified Communications Web API (UCWA) Server unterstützt, der auf dem Front-End-Server installiert ist. In der folgenden Abbildung ist die Registerkarte " **REACH** " des lync Server 2013 Tools zum Laden der Konfiguration dargestellt.

Verwenden Sie die Registerkarte **REACH** , um alle REACH-bezogenen Szenarien zu konfigurieren.

![Registerkarte "REACH".](images/JJ945594.65ccf6de-0e8d-47ba-93f3-9dcb39d3fd62(OCS.15).jpg "Registerkarte "REACH".")

1.  Klicken Sie auf die Schaltfläche **erweitert** neben **Allgemeine Einstellungen für REACH**. Legen Sie das Feld **UcwaTargetServerUrl** auf die Directorpool virtuelle IP (VIP) oder die Front-End-Pool VIP fest.

2.  Wählen Sie unter **Anwendungsfreigabe**, **Datenzusammenarbeit**und **Sofortnachrichten**den entsprechenden Wert für die **Auslastungsstufe**aus.

<div>


> [!NOTE]  
> In jedem der Szenarien befindet sich daneben eine Schaltfläche " <STRONG>erweitert</STRONG> ". Diese Schaltflächen ermöglichen den Zugriff auf spezifische Werte für jedes Szenario, das das Verhalten des lync Server 2013 Stress and Performance Tool (LyncPerfTool) ändert und die Anpassung aktiviert. Wenn die <STRONG>Auslastungsstufe</STRONG> <STRONG>Custom</STRONG>ist, wird für jedes der REACH-Szenarien anstelle der Standardeinstellung der im Feld <STRONG>ConversationsPerHour</STRONG> angegebene Wert verwendet.



</div>

Verwenden Sie die Registerkarte **Mobilität** , um alle mobilitätsbezogenen Szenarien zu konfigurieren.

![Registerkarte Mobilität.](images/JJ945594.4dd8f3e0-921c-48a5-8b23-2a0330d3c334(OCS.15).jpg "Registerkarte Mobilität.")

1.  Klicken Sie auf die Schaltfläche **erweitert** neben **Mobility (UCWA)**. Legen Sie das Feld **UcwaTargetServerUrl** auf die Directorpool virtuelle IP (VIP) oder die Front-End-Pool VIP fest.

2.  Wählen Sie in **Anwesenheits-\\und P2P-Chat-Audio**den entsprechenden Wert für die **Auslastungsstufe** aus, um die Mobilitäts Szenario-Simulation zu aktivieren.

<div>


> [!NOTE]  
> In jedem der Szenarien befindet sich daneben eine Schaltfläche " <STRONG>erweitert</STRONG> ". Diese Schaltflächen ermöglichen den Zugriff auf spezifische Werte für jedes Szenario, das das Verhalten des lync Server 2013 Stress and Performance Tool (LyncPerfTool) ändert und die Anpassung aktiviert. Wenn die <STRONG>Auslastungsstufe</STRONG> <STRONG>Custom</STRONG>ist, wird für jedes der REACH-Szenarien anstelle der Standardeinstellung der im Feld <STRONG>ConversationsPerHour</STRONG> angegebene Wert verwendet.



</div>

</div>

<div>

## <a name="summary"></a>Zusammenfassung

Die Registerkarte " **Zusammenfassung** " des lync Server 2013 Tools zum Laden der Konfiguration ist in der folgenden Abbildung dargestellt.

![Registerkarte Zusammenfassung.](images/JJ945594.c675e869-8ded-4195-8c2a-68d844fc96ad(OCS.15).jpg "Registerkarte Zusammenfassung.")

Auf der Registerkarte **Zusammenfassung** wird angegeben, welche Benutzer für welche Szenarien verwendet werden sollen. Benutzernummern Bereiche können manuell konfiguriert werden, indem das Kontrollkästchen Benutzer **definierte Benutzerbereichs Generierung aktivieren aktiviert** ist, und dann doppelklicken Sie auf das Szenario in der Tabelle mit dem **Benutzerbereich** , den Sie anpassen möchten. Überprüfen Sie (RunClient. bat) beim Starten eine Anmelde Verzögerung hinzufügen, um Verzögerungen in den generierten Batchdateien einzuschließen, die dem Anmelderate entsprechen. Dies ist hilfreich, um eine Serverüberlastung zu verhindern, wenn eine große Anzahl von Benutzern signiert wird. Klicken Sie auf **Dateien generieren**, und wählen Sie den Ordner aus, in dem die Konfiguration generiert werden soll. Ein Dialogfeld wie die folgende Abbildung wird angezeigt, wenn Ihre Dateien erfolgreich erstellt wurden.

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
