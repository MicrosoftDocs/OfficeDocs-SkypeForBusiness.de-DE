---
title: Cloud-Konsolidierung für Teams und Skype für Unternehmen
ms.author: crowe
author: crowe
manager: serdars
ms.reviewer: bjwhalen
ms.topic: article
ms.service:
- skype-for-business-online
- msteams
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_Help
- Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
description: In diesem Artikel wird das zu erzielen, Konsolidierung für Organisationen mit lokalen Deployment(s) von Skype Business (oder ein Lync), die gesuchte wechseln, um ihre UC-Arbeitslast Teams verschieben und/oder Skype für Business Online beschrieben.
ms.openlocfilehash: 09a19b884b67f9d6c3dbbe552f2576b6b5e68674
ms.sourcegitcommit: 4dac1994b829d7a7aefc3c003eec998e011c1bd3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/13/2018
ms.locfileid: "27247675"
---
# <a name="cloud-consolidation-for-teams-and-skype-for-business"></a>Cloud-Konsolidierung für Teams und Skype für Unternehmen

> [!Note]
> Dies ist eine Vorschauversion oder eine Vorabfunktion. 

Viele große Unternehmen haben mehr als einen lokalen Active Directory-Gesamtstruktur und in einigen Fällen haben Kunden mehrere Exchange und/oder Skype für die Bereitstellung von Business Server (oder Lync Server). Darüber hinaus auch Organisationen mit nur einer lokalen Gesamtstruktur selbst in einer ähnlichen Situation über eine Business Fusion oder Übernahme gefunden. Wie diese Kunden in der Cloud verschieben, möchten sie mehrere Instanzen einer angegebenen lokalen Arbeitslast in der Cloud in einer einzelnen Office 365-Mandanten konsolidieren. In diesem Artikel wird das zu erzielen, Konsolidierung für Organisationen mit mehreren lokalen Bereitstellungen von Skype für Unternehmen (oder Lync), die ihre UC-Arbeitslast mit der Microsoft-Cloud, z. B. verschieben möchten, Microsoft-Teams und/oder Skype für Business Online beschrieben.

In der Vergangenheit wurde die Anleitung für Kunden in dieser Situation zur Konsolidierung von lokalen Bereitstellungen zuerst und anschließend in der Cloud verschieben. Dieser Artikel beschreibt eine Lösung basierend auf neue Funktionen, der Organisationen mit mehreren Skype für Business Bereitstellungen einer Bereitstellung jeweils in einer einzelnen Office 365-Mandanten zu migrieren, ohne lokale ermöglicht während dies weiterhin möglich ist, Konsolidierung. Beachten Sie, dass selbst bei dieser neuen Funktionen, Skype für Business Online und Microsoft-Teams, nicht mehrere Skype für Business/Lync-Gesamtstrukturen in Hybridmodus mit einer einzelnen Office 365-Mandanten unterstützen. 

> [!Important]
> Bevor Sie dieses Handbuch für die Konfiguration verwenden, unbedingt lesen und verstehen, die [Einschränkungen](#limitations), wie sie Ihre Organisation beeinträchtigen können.

## <a name="overview-of-cloud-consolidation"></a>Übersicht über die Cloud Konsolidierung

Konsolidierung aller Benutzer lokal in der Cloud in einem einzelnen Office 365-Mandanten kann für jede Organisation mit mehreren Skype für Business-Bereitstellungen erzielt werden, vorausgesetzt, dass die folgenden wichtigen Anforderungen erfüllt sind:

- Es muss höchstens ein Office 365-Mandanten Beteiligten. Konsolidierung in Szenarien mit mehr als eine Office 365-Mandanten wird nicht unterstützt.
- Zu jedem Zeitpunkt in der lokalen nur eine Skype für Business Gesamtstruktur in Hybridmodus (Shared SIP-Adressraum) werden kann. Alle anderen lokalen Skype für Business Gesamtstrukturen muss der lokale bleiben (und vermutlich miteinander federated). Beachten Sie, diese anderen lokalen Organisationen *können* Synchronisierung mit AAD bei Bedarf mit [neuen Funktionen in online SIP-Domänen deaktivieren](https://docs.microsoft.com/en-us/powershell/module/skype/disable-csonlinesipdomain?view=skype-ps) ab Dezember 2018 verfügbar.

Kunden mit der Bereitstellung von Skype für Unternehmen in mehreren Gesamtstrukturen müssen alle Benutzer über einen einzelnen Hybrid Skype für Business Gesamtstruktur vollständig einzeln in der Office 365-Mandanten mithilfe von Funktionalität, freigegebenen SIP-Adressraum migrieren, und deaktivieren Sie Hybrid mit Lokale Bereitstellung, vor dem Verschieben auf das nächste Migration: Skype für die Bereitstellung von Business lokal. Bleiben lokale Benutzer vor, die in die Cloud migriert werden, in den Verbund mit anderen Benutzern, die nicht in der gleichen Benutzer lokalen Verzeichnis dargestellt werden.  

## <a name="canonical-example-of-cloud-consolidation"></a>Kanonische Beispiel einer Cloud-Konsolidierung

Berücksichtigen Sie eine Organisation mit zwei separaten federated lokalen Bereitstellungen von Skype für Unternehmen, die sie online in Microsoft-Teams, konsolidieren möchte oder Skype für Business Online.


|Details der ursprünglichen Zustand |Details der gewünschten Zustand |
|---------|---------|
|<ul><li>2 unabhängigen Skype für Unternehmen lokalen Bereitstellungen in separaten Active Directory-Gesamtstrukturen<li>Höchstens 1 Gesamtstruktur befindet sich in Hybrid mit Skype für Business Online <li> Strukturieren sind miteinander Verbundpartner. <li>Benutzer werden über diesen Gesamtstrukturen nicht synchronisiert.<li> Die Org möglicherweise ein Office 365-Mandanten und kann in Azure Active Directory Directory synchronisieren</ul>|<ul> <li>Office 365-Mandanten 1<li>Keine weiteren lokalen Bereitstellungen, also keine verbleibenden hybrid<li>Alle Benutzer aus lokal in Skype für Business Online, verwaltet und optional möglicherweise nur Teams-Benutzer <li>Keine lokale Speicherbedarf von Skype für Unternehmen an einer beliebigen Stelle <li>Benutzer weisen weiterhin lokale-Authentifizierung</ul> |

![Konsolidieren von zwei separaten federated lokale Bereitstellungen](../media/cloudconsolidationfig1.png)  

Die grundlegenden Schritte zum Abrufen von den ursprünglichen Zustand auf den gewünschten Endstatus sind unten aufgeführt.  Beachten Sie, dass einige Organisationen finden können, dass ihre Ausgangspunkt irgendwo in der Mitte folgendermaßen ist. Finden Sie weiter unten in diesem Artikel unter [anderen Ausgangspunkte](#other-starting-points). Schließlich kann in einigen Fällen die Reihenfolge, je nach Bedarf angepasst werden. [Key-Einschränkungen und Grenzen](#limitations) werden später beschrieben.

1.  Rufen Sie ein Office 365-Mandanten, wenn noch nicht vorhanden ist.
2.  Stellen Sie sicher, dass alle relevante SIP-Domänen über beide lokalen Bereitstellungen überprüften Office 365-Domänen sind.
3.  Wählen Sie einen Skype für die Business-Bereitstellung, die mit Office 365 Hybrid werden. In diesem Beispiel verwenden wir OriginalCompany. <span>com.
4.  [Aktivieren AAD Connect für die Gesamtstruktur](configure-azure-ad-connect.md) , die zuerst Hybrid werden (OriginalCompany.<span> com). 
5.  Wenn Sie Teams in Ihrer Organisation einführen, legen Sie die gesamte Mandanten Richtlinie für [TeamsUpgradePolicy](https://docs.microsoft.com/en-us/powershell/module/skype/grant-csteamsupgradepolicy) SfBWithTeamsCollab oder eine der anderen SfB Modi (SfBOnly oder SfBWithTeamsCollabAndMeetings). Dies ist ein entscheidender Faktor, um sicherzustellen, dass routing von Anrufen und chats von Benutzern, die in Teams nur für Benutzer zu verschieben, die lokal bleiben.
6.  Es wird empfohlen, zu diesem Zeitpunkt (jedoch noch nicht erforderlich, bis Schritt 11) [AAD Connect für der anderen Gesamtstruktur](cloud-consolidation-aad-connect.md) aktivieren (AcquiredCompany.<span> com). Vorausgesetzt, dass in beiden Gesamtstrukturen AAD verbinden aktiviert ist, sieht die Org wie in **[Abbildung A](#figure-a)**, die möglicherweise ein allgemeiner Ausgangspunkt für einige strukturieren. 
7.  Für alle SIP-Domänen, die von anderen lokalen Bereitstellungen gehostet wird (in diesem Fall AcquiredCompany.<span> com), [Deaktivieren Sie diese SIP-Domänen in Skype für Business Online](https://docs.microsoft.com/en-us/powershell/module/skype/disable-csonlinesipdomain) mit `Disable-CsOnlineSipDomain` in PowerShell. (Dies ist ein neuer Funktionen ab Dezember 2018.)
8.  [Konfigurieren von Skype für hybride Business](configure-federation-with-skype-for-business-online.md) für OriginalCompany. <span>com (einer Bereitstellung, die noch online SIP-Domänen aktiviert wurde).
9.  In der hybridbereitstellung (OriginalCompany.<span> com), [Verschieben von Benutzern von Skype für Unternehmen lokal in der Cloud](move-users-between-on-premises-and-cloud.md) zu starten (, ob nur oder nicht-Teams), damit Konto in Skype für Business Online verwaltet wird. Jetzt sieht die Organisation wie in **[Abbildung B](#figure-b)**. Die wichtigsten Änderungen von Abbildung A sind:
    - Benutzer aus beiden lokalen Verzeichnissen befinden sich nun im AAD.
    - AcquiredCompany. <span>com ist eine deaktivierte online SIP-Domäne.
    - Einige Benutzer wurden online in beiden Skype für Business Online oder Teams verschoben. (Siehe Lila Benutzer a)
10. Nachdem alle Benutzer in der Cloud für OriginalCompany [Deaktivieren Hybrid mit der Skype für Business lokale Bereitstellung](cloud-consolidation-disabling-hybrid.md) verschoben werden. <span>com in Office 365:  
    - Geteilte Domäne in Office 365-Mandanten zu deaktivieren.
    - Deaktivieren der Möglichkeit zur Kommunikation mit Office 365 in OriginalCompany. <span>com lokalen.
    - Aktualisieren Sie DNS-Einträge für OriginalCompany. <span>com, zeigen Sie auf Office 365.
11. Falls nicht bereits [AAD Connect für den nächsten Gesamtstruktur aktivieren](cloud-consolidation-aad-connect.md) geschehen, die Hybriden wird (AcquiredCompany.<span> com). Zu diesem Zeitpunkt sieht die Organisation wie in **[Abbildung C](#figure-c)**. Eine andere allgemeine Ausgangspunkt für einige Organisationen möglicherweise. 
12. In PowerShell, Hybrid-und AcquiredCompany die wird [die SIP-Domänen für die nächsten lokale Bereitstellung zu aktivieren](https://docs.microsoft.com/en-us/powershell/module/skype/enable-csonlinesipdomain?view=skype-ps) . <span>com. Dies erfolgt mithilfe von `Enable-CsOnlineSipDomain`, die neue Funktionalität ab Dezember 2018 verfügbar ist.
13. Wenn Sie geschlossene Verbund verwenden, müssen Sie alle SIP-Domänen hinzufügen (ausgenommen *. microsoftonline.com) des reinen online Mandanten als zulässigen Domänen in der **gleichen** Office 365. Beachten Sie, dass kann es einige Zeit, bevor die Änderung wirksam und keine Beschädigungen frühzeitig und dabei vorhanden ist, damit wir empfehlen dies dauern im Vorfeld mit Schritt 14.
14. Aktualisieren Sie die lokale Umgebung, um alle SIP-Domänen aus der online-Mandanten akzeptieren, damit sie übereinstimmen.
    - [Aktualisieren des SAN in alle Edgeserver-Zertifikate](cloud-consolidation-edge-certificates.md) auf den gleichen Wert wie zuvor werden sowie Werte für alle vorhandenen online SIP-Domänen (mit Ausnahme von *. microsoftonline.com), in diesem Fall Sip.OriginalCompany. <span>com.
    - Stellen Sie sicher, dass OriginalCompany. <span>com ist eine [zulässige Domäne](https://docs.microsoft.com/en-us/powershell/module/skype/new-csalloweddomain) in der lokalen Bereitstellung AcquiredCompany. Fügen Sie zugelassenen Domänen hinzu.
15. [Aktivieren von Skype für hybride Business](configure-federation-with-skype-for-business-online.md) zwischen lokalen AcquiredCompany. <span>com und der Cloud.
16. Wie gewünscht [Migrieren von Benutzern von lokalen in die Cloud](move-users-between-on-premises-and-cloud.md). Sie können Migrieren von Benutzern entweder direkt auf [TeamsOnly](/microsoftteams/teams-and-skypeforbusiness-coexistence-and-interoperability) Modus oder Sie können zuerst in migrieren Skype für Business Online. **[Abbildung D](#figure-d)** ähnelt die Organisation, während dieses Zustands.
17. Nachdem alle Benutzer migriert werden, zu *der Organisation reinen Cloud* [Hybrid mit der lokalen Umgebung deaktivieren](cloud-consolidation-disabling-hybrid.md) !

Die folgenden Diagramme zeigen die Konfiguration unter verschiedenen Hauptpunkte während dieses Vorgangs.

##### <a name="figure-a"></a>Abbildung A:

- Beide Organisationen Sync über AAD Connect, sodass AAD enthält nun alle Benutzer aus beiden lokale Bereitstellungen.
- Alle Benutzer, der lokalen verwaltet.  
- Skype für hybride Business ist noch *nicht* konfiguriert.
- Wenn Benutzer in einer Bereitstellung Teams verwenden, sie nicht den Verbund mit anderen (oder jede Organisation) möglich, noch wird Interoperabilität mit jeder Skype für Unternehmensbenutzer haben. Klicken Sie in dieser Phase empfiehlt Microsoft Teams nur für Kanäle verwenden.<br><br>
    ![Abbildung A-Diagramm](../media/cloudconsolidationfiga.png)

##### <a name="figure-b"></a>Abbildung B:

- AcquiredCompany. <span>com ist eine [deaktiviert](https://docs.microsoft.com/en-us/powershell/module/skype/disable-csonlinesipdomain) online SIP-Domäne. Alle Benutzer in der lokalen sind. Wenn sie Teams verwenden, müssen sie nicht den Verbund oder die Interoperabilität. Klicken Sie in dieser Phase empfiehlt Microsoft Teams nur für Kanäle verwenden.
- Skype für hybride Business wurde für eines der lokalen Organisation aktiviert.
- Einige Benutzer in der hybridorganisation wurden in die Cloud (Benutzer A wie Lila unterlegt) verschoben. Diese Benutzer kann entweder Skype für Business Online-Benutzern oder Teams nur Benutzer mit vollständige Interoperabilität und Unterstützung für Identitätsverbund.<br><br>
    ![Abbildung B-Diagramm](../media/cloudconsolidationfigb.png)

##### <a name="figure-c"></a>Abbildung C:

- Alle Benutzer aus OriginalCompany. <span>com sind nun in der Cloud (die in Skype für Business Online verwaltet werden). Es wird empfohlen, dass sie auch nur Teams werden.
- Skype Business hybridkonfiguration mit der OriginalCompany. <span>COM-Bereitstellung deaktiviert wurde. Die lokale Bereitstellung wurde entfernt.
- Wenn AcquiredCompany. <span>com wurde nicht zuvor mit AAD synchronisieren, um fortgeführt werden hier muss es jetzt synchronisiert werden. Aber es ist nicht noch Hybrid (freigegebenen SIP-Adressraums) und, bis die Organisation bereit, zu Hybrid verschieben ist, die online SIP-Domäne für die rein lokalen Organisation (AcquiredCompany.com) sollte bleiben weiterhin deaktiviert, sodass online Teams-Benutzern kommunizieren können der lokale Benutzer.<br><br>
    ![Abbildung C-Diagramm](../media/cloudconsolidationfigc.png)

##### <a name="figure-d"></a>Abbildung D:

- AcquiredCompany. <span>com jetzt als eine online SIP-Domäne aktiviert ist.
- Der lokale wird aktualisiert, sodass OriginalCompany akzeptieren. <span>com. (Beide zulässigen Domänen und Edgeserver-Zertifikate werden aktualisiert).
- Freigegebenen SIP-Adressraums ist zwischen AcquiredCompany aktiviert. <span>com und Office 365-Mandanten.
- Möglicherweise wurden einige Benutzer in der hybridorganisation zur Cloud, wie Benutzer D unten (angegeben durch Lila Schattierung) verschoben.<br><br>
    ![Abbildung D Diagramm](../media/cloudconsolidationfigd.png)

## <a name="other-starting-points"></a>Andere Ausgangspunkte

Die Schritte im obigen Beispiel wird davon ausgegangen, dass die Organisation mit zwei federated lokale Bereitstellungen mit keine Anwesenheitsinformationen für Office 365 beginnt. Jedoch einige Organisationen möglicherweise eine vorhandene Office 365-Bilanz und können verschiedene Einstiegspunkte in die oben genannten Sequenz vorhanden sein. Es gibt vier gebräuchlichen Konfigurationen:

- Mehrere lokale föderierten Organisationen mit keine Office 365-Mandanten. In diesem Fall mit Schritt 1 beginnen.
- Mandanten für mehrere federated lokalen Organisationen, die bereits in einer einzelnen Azure AD mehrere Skype für Business Gesamtstruktur synchronisieren. Eine solche eine Organisation ähnelt die hypothetische Organisation in Abbildung A, die Schritte 1 bis 6 abgeschlossen ist und sollte mit Schritt 7 beginnen.
- Einer hybridorganisation, die Verbindung mit 1 oder mehrere andere rein lokalen Organisationen, Synchronisieren von denen keines mit AAD. Ein Unternehmen dieser Art würde die hypothetische Organisation in **Abbildung E**, auf der unten gezeigten ähneln.
    - Diese Organisation ist ähnlich wie in Abbildung B, die Schritte 1 bis 9, mit Ausnahme von abgeschlossen wurde:
        - Seine nicht-hybridbereitstellungen Skype für Business-Bereitstellungen sind *nicht* noch in Azure Active Directory synchronisiert wird.
        -  Online SIP-Domänen sind noch nicht deaktiviert. 
    - Diese Unternehmen sollte entweder:
        - Schließen Sie der Migration der vorhandenen hybridorganisation ab, und geben Sie die oben angegebene Reihenfolge in Schritt 10.  OR
        - Falls gewünscht andere Synchronisierung wird Skype für Business Gesamtstrukturen in AAD vor dem Abschluss der Migration der hybridorganisation, und klicken Sie dann die Organisation ausführen muss Schritt 7 (deaktivieren alle online SIP-Domänen in anderen lokalen Skype für Business-Bereitstellung wird Synchronisierung in AAD) und anschließend aktivieren AAD verbinden und nur fahren Sie mit Schritt 10 (außer Betrieb nehmen die ursprünglichen hybridbereitstellung).       
                **Abbildung E**<br>
                ![Abbildung E Diagramm](../media/cloudconsolidationfige.png)
- Eine reine Skype für Business Online-Organisation (der kann möglicherweise nicht Teams verwenden), die Verbindung mit einer separaten lokalen Skype für Business-Organisation. Sobald diese Organisation die online SIP-Domäne für die lokale Organisation deaktiviert und für die lokale Skype für Unternehmen AAD verbinden ermöglicht, ähnelt es die hypothetische Organisation dargestellt in **[Abbildung C](#figure-c)** , die die Schritte abgeschlossen wurde 1 bis 11.

## <a name="limitations"></a>Einschränkungen

- Es muss höchstens ein Office 365-Mandanten Beteiligten. Konsolidierung in Szenarien mit mehr als eine Office 365-Mandanten wird nicht unterstützt.
- Nur einen lokalen, dass Skype für Business Gesamtstruktur zu einem Zeitpunkt in Hybridmodus (freigegebenen SIP-Adressraums) werden kann. Alle anderen lokalen Skype für Business Gesamtstrukturen muss rein lokalen bleiben und untereinander und die Office 365-Mandanten federated werden sollte.
- Vor der, die in die Cloud migriert werden, ist eine asymmetrische wünschen für Benutzer in dieser Bereitstellung, da nicht alle Benutzer in online dargestellte lokalen sind:
    - Die Erfahrung kann wie folgt summiert:
        - Jeder Benutzer online verwaltet interagieren mit lokalen Benutzern in hybridumgebung ein, als ob der Benutzer Hybrid ist.
        - Der lokale Benutzer in der hybridbereitstellung interagiert mit online-Benutzern, die in ihrer lokalen Verzeichnis dargestellt werden, als wären sie Hybrid. 
        - Lokale Benutzer in der hybridbereitstellung interagiert mit online-Benutzern, die nicht in dargestellt werden lokale AD wie Identitätsverbund.
    - In **[Abbildung D](#figure-d)** oben ist Benutzer E lokale in AcquiredCompany. <span>com.  Benutzer E interagiert mit dem Benutzer D (nur verwaltet) mithilfe der standard-Hybrid-Erfahrung, aber Benutzer E müssen eine Verbund Erfahrung mit Benutzer A, B und C, da sie nicht im lokalen Verzeichnis dargestellt werden. Benutzer A, B und C werden jedoch Interaktion mit Benutzer E, als wäre der Benutzer in Hybrid.
    - Auswirkungen der Interaktion Hybrid im Vergleich zu den Verbund wird:
        - Anwesenheit ist nicht automatisch für Verbundbenutzer abonniert, wenn der Benutzer als Kontakt markiert ist.
        - Die anrufweiterleitung funktioniert nicht zwischen Partnerdomänen.
        - Anruf weiterleiten Szenarien sind geringerem.
        - Einschränkung kann auf verbunddatenverkehr angewendet werden.
- Angesichts dieser asymmetrischen Erfahrung, ist offizielle Unterstützung für Anruffunktionen in standortübergreifenden Szenarien zwischen einem lokale Benutzer und einer Cloud-Benutzer, die nicht im lokalen Verzeichnis Peer-to-Peer-nur begrenzt. 
    - Rufen Sie Weiterleitung, weiterleiten, Anruf Warteschlangen, usw. zwischen diesen Benutzern wird nicht unterstützt.
    - Diese aufrufenden nicht unterstützte Szenarien weiterhin aktiviert angezeigt, aber in vielen Fällen werden sie auf unvorhersehbare Weise fehl. 
    - In **[Abbildung D](#figure-d)** oben genannten Benutzer E: lokal und werden nur als Peer-to-Peer-Anrufe mit Benutzern A, B oder C unterstützt. (Anrufe D-Benutzer müssen nicht eingeschränkte Unterstützung.)  Nachdem der lokalen Benutzer E in der Cloud verschoben wird, gilt jedoch diese Einschränkung nicht mehr.
- Wenn Sie mehr als eine Bereitstellung von Skype für Business Server 2019 in Ihrer Umgebung verfügen, können diese Bereitstellung nur 1 Organisationseinheit automatische Telefonzentrale verwenden, da dieses Feature Skype hybridkonfiguration Business Server erfordert konfiguriert werden. 
- Die Reihenfolge der einige der vorherigen Schritte kann angepasst werden. Die wichtigste Anforderung, die erfüllt sein muss, ist, die, wenn alle diese zutreffen:
    - Mehr als einen lokalen Skype für Business Gesamtstruktur mit einer einzelnen Mandanten AAD synchronisieren
    - Geteilte Domäne ist mit einer lokalen Gesamtstruktur aktiviert.
    - Mindestens ein Benutzer in der hybridorganisation wurde in die Cloud migriert.<br>   Klicken Sie dann, *müssen* Sie alle anderen online SIP-Domänen aus anderen lokalen Skype für Business Gesamtstruktur zu deaktivieren. Andernfalls wird in einer Richtung Verbund zwischen online-Benutzern in Hybrid-Organisation und lokale Benutzer in anderen Organisationen unterbrochen.

## <a name="implications"></a>Bedeutung

- Da Beschränkungen bei der Unterstützung für erweiterte Anruffunktionen vorhanden sind, wie oben beschrieben, **Organisationen sollten diese asymmetrischen Zustände behandelt, als ausgelastete im Rahmen der Migration, und sie nicht als stabilen Zustand ausüben**.  
- Organisationen mit mehreren lokalen Skype für Business-Bereitstellungen sollten im Allgemeinen starten bei einer Bereitstellung, die vollständig in die Cloud migriert werden kann, sodass Konsolidierung fortgesetzt werden kann. Es wird davon ausgegangen, dass in einigen Fällen Holdouts von bestimmten Benutzergruppen werden, für die wen diese noch nicht Teams verschieben verwendbar ist. Wenn dies in Szenarien mit mehreren Skype für Business Gesamtstrukturen von Belang ist, starten Sie die Migration mit einer anderen Gesamtstruktur, die diese Einschränkung nicht nach Möglichkeit verfügt.
- Beim Verschieben von lokalen in die Cloud sind Benutzer, die Delegierung Beziehungen und/oder sind in der Regel die anrufweiterleitung beteiligt, den Szenarien zusammen als Einheit verschoben werden soll.

## <a name="considerations-for-moving-to-teamsonly-mode"></a>Überlegungen zum Verschieben von TeamsOnly-Modus

Wenn Sie Benutzer aus lokal in der Cloud in einer hybridumgebung verschieben, können Sie sie in entweder Skype für den Modus nur Business oder TeamsOnly zu verschieben. *Wenn Sie in den Modus TeamsOnly Benutzer verschieben möchten, müssen Sie in diesem Abschnitt zuerst zu lesen.*

- Wenn Sie einen Benutzer TeamsOnly Modus zuweisen, landen alle Chats und Anrufe von einem anderen Benutzer Teams-Client des Benutzers. 
- Um sicherzustellen ordnungsgemäßes routing des chats und Anrufe zwischen Benutzern, die TeamsOnly sind und Benutzer, die noch für Unternehmen lokal, Skype verwenden möchten, müssen Sie sicherstellen, dass der lokale Benutzer verfügen, nicht mit einem der Modi SfB TeamsUpgradePolicy, sondern Inseln (Dies ist die Standardeinstellung ). 
    - Dazu *müssen Sie zuerst Ihrem Mandanten globale Instanz des TeamsUpgradePolicy auf einen der folgenden Werte festlegen*:
        - SfBWithTeamsCollab (empfohlen)
        - SfBWithTeamsCollabAndMeetings
        - SfBOnly
    - Sie können die Mandanten geltende Richtlinie erteilen, mit dem folgenden Befehl:<br>`Grant-CsTeamsUpgradePolicy -PolicyName SfBWithTeamsCollab -Global`
    - Hinweis: Derzeit, müssen Sie dies auf einem Mandanten-Ebene ausführen, da die Richtlinie kann nicht für einzelne Benutzer zugewiesen werden, die nicht über eine SIP-Adresse in online-Verzeichnis verfügen. Während Sie online SIP-Domänen für Ihre lokale reine Deployment(s) deaktiviert haben, werden nicht Benutzern in diesen Domänen SIP-Adressen in der online Directory entwurfsbedingt verfügen. Daher ist die einzige Möglichkeit, die Richtlinie auf die lokale Benutzer anzuwenden, indem auf der Ebene der Mandant zuweisen. Im Gegensatz dazu in der Hybriden haben Bereitstellung Benutzer eine SIP-Adresse in das Verzeichnis online, sodass sie explizit eine Richtlinie zugewiesen werden können falls gewünscht wird, dass sie einen anderen Wert als die globale Richtlinie Mandanten besitzen.
- Der Client Teams UX berücksichtigt noch nicht die SfB Kommunikationsmodi TeamsUpgradePolicy. Beispielsweise ist in der folgenden Modi Anruf und Chat Initiierung in Teams derzeit möglich, zwar in der Zukunft wird nicht der Fall sein. Dies kann erkennbar ist Benutzer führen, da Antworten manchmal in Teams und manchmal Skype für Unternehmen, je nach den sorgt können. Es wird empfohlen, dass Sie separat Anrufe deaktivieren und chat über TeamsMessagingPolicy und TeamsCallingPolicy für Benutzer, die weiterhin lokal sind.

## <a name="see-also"></a>Siehe auch

[Aktualisieren des Edge-Zertifikats](cloud-consolidation-edge-certificates.md)

[Update AAD Herstellen einer Verbindung mit mehr als einer Gesamtstruktur einschließen](cloud-consolidation-aad-connect.md)

[Deaktivieren Sie zum Abschließen der Migration zur Cloud hybrid](cloud-consolidation-disabling-hybrid.md)