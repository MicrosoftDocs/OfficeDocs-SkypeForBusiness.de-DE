---
title: Cloudkonsolidierung für Teams und Skype for Business
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.reviewer: bjwhalen
ms.topic: article
ms.prod: skype-for-business-itpro
search.appverid: MET150
ms.collection:
- Hybrid
- M365-voice
- M365-collaboration
- Teams_ITAdmin_Help
- Adm_Skype4B_Online
audience: ITPro
f1.keywords:
- NOCSH
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
description: In diesem Artikel wird beschrieben, wie Sie diese Konsolidierung für Organisationen mit lokalen Bereitstellungen von Skype for Business (oder Lync) erreichen können, die ihre UC-Arbeitslast auf Teams und/oder Skype for Business Online verschieben wollen.
ms.openlocfilehash: 94bd2697e87a7a007cc57f63f5ecd96852705c41
ms.sourcegitcommit: 7ebcff93ecbdc064414d7110e182b29371ca4f1f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/06/2021
ms.locfileid: "52237601"
---
# <a name="cloud-consolidation-for-teams-and-skype-for-business"></a>Cloudkonsolidierung für Microsoft Teams und Skype for Business

Viele Großunternehmen verfügen über mehr als eine lokale AD-Gesamtstruktur, und in einigen Fällen verfügen Kunden über mehr als eine Bereitstellung von Exchange und/oder Skype for Business Server (oder Lync Server). Darüber hinaus können sich auch Organisationen mit nur einer lokalen Gesamtstruktur bei einer Fusion oder Übernahme in einer ähnlichen Situation befinden. Wenn diese Kunden in die Cloud wechseln, möchten sie die mehreren Instanzen einer bestimmten lokalen Arbeitsauslastung in der Cloud in einer einzigen Microsoft 365 oder Office 365 konsolidieren. In diesem Artikel wird beschrieben, wie Sie diese Konsolidierung für Organisationen mit mehreren lokalen Bereitstellungen von Skype for Business (oder Lync) erreichen können, die ihre UC-Workload in die Microsoft Cloud verschieben möchten, z. B. Microsoft Teams und/oder Skype for Business Online.

[!INCLUDE [sfbo-retirement-skype](../../Hub/includes/sfbo-retirement.md)]

In der Vergangenheit war es für Kunden in dieser Situation so, dass sie Bereitstellungen zuerst lokal konsolidieren mussten und erst dann einen Umstieg in die Cloud vollziehen konnten. Obwohl dies weiterhin eine Option ist, wird in diesem Artikel eine Lösung beschrieben, die auf neuen Funktionen basiert, mit der Organisationen mit mehreren Skype for Business-Bereitstellungen eine Bereitstellung gleichzeitig in eine einzelne Microsoft 365- oder Office 365-Organisation migrieren können, ohne dass eine lokale Konsolidierung erforderlich ist. Beachten Sie, dass Skype for Business Online und Microsoft Teams auch bei dieser neuen Funktionalität nicht mehrere Skype for Business/Lync-Gesamtstrukturen im Hybridmodus mit einer einzelnen Microsoft 365 oder Office 365 unterstützen. 

> [!Important]
> Bevor Sie dieses Handbuch für die Konfiguration verwenden, sollten Sie unbedingt die Einschränkungen überprüfen und [verstehen,](#limitations)da sie sich auf Ihre Organisation auswirken können.

## <a name="overview-of-cloud-consolidation"></a>Übersicht über die Cloudkonsolidierung

Die Konsolidierung aller Benutzer aus der lokalen Cloud in einer einzigen Microsoft 365- oder Office 365-Organisation kann für jede Organisation mit mehreren Skype for Business-Bereitstellungen erreicht werden, sofern die folgenden zentralen Anforderungen erfüllt sind:

- Es muss in der Organisation Microsoft 365 oder Office 365 sein. Die Konsolidierung in Szenarien mit mehreren Organisationen wird nicht unterstützt.
- Es darf jeweils nur eine lokale Skype for Business-Gesamtstruktur im Hybridmodus (freigegebener SIP-Adressraum) vorhanden sein. Alle anderen lokalen Skype for Business-Gesamtstrukturen müssen lokal bleiben (und vermutlich miteinander verbunden sein). Beachten Sie, dass diese  anderen lokalen Organisationen AAD bei Bedarf mit neuen Funktionen synchronisieren können, um ab Dezember 2018 verfügbare [Online-SIP-Domänen](/powershell/module/skype/disable-csonlinesipdomain) zu deaktivieren.

Kunden mit Bereitstellungen von Skype for Business in mehreren Gesamtstrukturen müssen alle Benutzer einer einzelnen Hybrid-Skype for Business-Gesamtstruktur vollständig mithilfe der Funktionalität für gemeinsam genutzten SIP-Adressraum in die Microsoft 365- oder Office 365-Organisation migrieren und dann die Hybridbereitstellung mit dieser lokalen Bereitstellung deaktivieren, bevor sie die nächste lokale Skype for Business-Bereitstellung migrieren. Vor der Migration in die Cloud verbleiben lokale Benutzer in einem Verbundstatus mit allen Benutzern, die nicht im lokalen Verzeichnis des gleichen Benutzers dargestellt sind.  

## <a name="canonical-example-of-cloud-consolidation"></a>Kanonisches Beispiel für die Cloudkonsolidierung

Betrachten Sie eine Organisation mit zwei separaten lokalen Verbundbereitstellungen von Skype for Business, die sie online in Microsoft Teams oder Skype for Business konsolidieren möchten.


|Originalzustandsdetails |Gewünschte Statusdetails |
|---------|---------|
|<ul><li>2 unabhängige Skype for Business lokalen Bereitstellungen in separaten AD-Gesamtstrukturen<li>Mindestens eine Gesamtstruktur befindet sich in Hybrid mit Skype for Business Online <li> Organisationen sind miteinander verkn nnen <li>Benutzer werden nicht über diese Gesamtstrukturen synchronisiert<li> Die Organisation kann über eine Microsoft 365 oder Office 365 verfügen und ihr Verzeichnis mit Azure AD synchronisieren.</ul>|<ul> <li>1 Microsoft 365 oder Office 365 Organisation<li>Keine lokalen Bereitstellungen mehr, sodass keine Hybridbereitstellung mehr übrig bleibt<li>Alle lokalen Benutzer werden in Skype for Business Online Teams werden <li>Keine lokale Stellfläche von Skype for Business überall <li>Benutzer verfügen weiterhin über lokale Authentifizierung</ul> |

![Konsolidieren von zwei separaten lokalen Verbundbereitstellungen](../media/cloudconsolidationfig1.png)  

Die grundlegenden Schritte zum Erreichen des ursprünglichen Zustands in den gewünschten Endzustand sind unten aufgeführt.  Beachten Sie, dass einige Organisationen feststellen, dass ihr Ausgangspunkt sich irgendwo in der Mitte dieser Schritte befindet. Weitere [Startpunkte](#other-starting-points)finden Sie weiter später in diesem Artikel. Schließlich kann die Reihenfolge in einigen Fällen je nach Bedarf angepasst werden. [Wichtige Einschränkungen und Einschränkungen](#limitations) werden später beschrieben.

1.  Erhalten Sie Microsoft 365 oder Office 365 Organisation, wenn noch keine vorhanden ist.
2.  Stellen Sie sicher, dass alle relevanten SIP-Domänen in beiden lokalen Bereitstellungen Microsoft 365 oder Office 365 werden.
3.  Wählen Sie eine Skype for Business, die hybrid mit Microsoft 365 oder Office 365. In diesem Beispiel verwenden wir OriginalCompany. <span> com.
4.  [Aktivieren sie Verbinden AAD für die Gesamtstruktur,](configure-azure-ad-connect.md) die zuerst hybrid wird (OriginalCompany. <span> com). 
5.  Wenn Sie Teams in Ihrer Organisation einführen, legen Sie die mandantenweite Richtlinie für [TeamsUpgradePolicy](/powershell/module/skype/grant-csteamsupgradepolicy) auf SfBWithTeamsCollab oder einen der anderen SfB-Modi (SfBOnly oder SfBWithTeamsCollabAndMeetings) festgelegt. Dies ist wichtig, um das Routing von Anrufen und Chats von Benutzern sicherzustellen, die zu Teams nur an Benutzer, die lokal bleiben.
6.  Es wird an dieser Stelle empfohlen (aber noch nicht erforderlich, bis Schritt 11), [AAD-Verbinden](cloud-consolidation-aad-connect.md) für die andere Gesamtstruktur zu aktivieren (AcquiredCompany. <span> com). Wenn AAD Verbinden in beiden Gesamtstrukturen aktiviert ist, sieht die Organisation wie **[Abbildung A](#figure-a)** aus, was für einige Organisationen ein gemeinsamer Ausgangspunkt sein kann. 
7.  Für alle SIP-Domänen, die von anderen lokalen Bereitstellungen gehostet werden (in diesem Fall AcquiredCompany. <span> com), [deaktivieren Sie diese SIP-Domänen in Skype for Business Online](/powershell/module/skype/disable-csonlinesipdomain) mithilfe von `Disable-CsOnlineSipDomain` PowerShell. (Dies ist neue Funktionalität ab Dezember 2018.)
8.  [Konfigurieren Skype for Business Hybrid für](configure-federation-with-skype-for-business-online.md) OriginalCompany. <span> com (die einzige Bereitstellung, für die noch Online-SIP-Domänen aktiviert sind).
9.  In der Hybridbereitstellung (OriginalCompany. <span> com), beginnen [Sie,](move-users-between-on-premises-and-cloud.md) Benutzer von Skype for Business lokal in die Cloud zu verschieben (unabhängig davon, ob Teams Nur oder nicht), damit das Konto in Skype for Business Online gespeichert wird. Nun sieht die Organisation wie **[Abbildung B aus.](#figure-b)** Die wichtigsten Änderungen von Abbildung A sind:
    - Benutzer aus beiden lokalen Verzeichnissen befinden sich jetzt in AAD.
    - AcquiredCompany. <span> com ist eine deaktivierte Online-SIP-Domäne.
    - Einige Benutzer wurden online zu Skype for Business Online oder Teams. (Siehe lila Benutzer A.)
10. Nachdem alle Benutzer in die Cloud verschoben wurden, deaktivieren Sie die Hybridbereitstellung Skype for Business lokalen [Bereitstellung](cloud-consolidation-disabling-hybrid.md) für OriginalCompany. <span> com aus Office 365:  
    - Deaktivieren Sie die geteilte Domäne in Microsoft 365 oder Office 365 Organisation.
    - Deaktivieren Sie die Möglichkeit, mit Microsoft 365 oder Office 365 in OriginalCompany zu kommunizieren. <span> com lokal.
    - Aktualisieren von DNS-Einträgen für OriginalCompany. <span> com, um auf Microsoft 365 oder Office 365.
11. Wenn noch nicht geschehen, [aktivieren Sie AAD Verbinden für](cloud-consolidation-aad-connect.md) die nächste Gesamtstruktur, die hybrid wird (AcquiredCompany. <span> com). An diesem Punkt sieht die Organisation wie **[Abbildung C aus.](#figure-c)** Dies kann ein weiterer gemeinsamer Ausgangspunkt für einige Organisationen sein. 
12. Aktivieren Sie in PowerShell [die SIP-Domänen für](/powershell/module/skype/enable-csonlinesipdomain) die nächste lokale Bereitstellung, die hybrid verwendet wird, AcquiredCompany. <span> com. Dies erfolgt mithilfe `Enable-CsOnlineSipDomain` von , das ist neue Funktionalität, die ab Dezember 2018 verfügbar ist.
13. Wenn Sie einen geschlossenen Verbund verwenden, müssen Sie alle SIP-Domänen (mit Ausnahme von .microsoftonline.com) des reinen Online-Mandanten als zulässige Domänen in denselben Microsoft 365 oder \* Office 365.  Beachten Sie, dass es einige Zeit dauern kann, bis die Änderung wirksam wird, und es besteht kein Schaden daran, dies frühzeitig zu tun. Daher empfehlen wir, dies bereits im Vorfeld des Wechsels zu Schritt 14 zu tun.
14. Aktualisieren Sie die lokale Umgebung so, dass alle SIP-Domänen vom Online-Mandanten akzeptiert werden, damit sie übereinstimmen.
    - [Aktualisieren Sie das SAN in](cloud-consolidation-edge-certificates.md) allen Edgezertifikaten auf denselben Wert wie zuvor, plus Werte für alle vorhandenen #A0 (außer *.microsoftonline.com), in diesem Fall Sip.OriginalCompany. <span> com.
    - Stellen Sie sicher, dass OriginalCompany. <span> com ist eine [zulässige Domäne](/powershell/module/skype/new-csalloweddomain) in der lokalen Bereitstellung AcquiredCompany. Hinzufügen zulässiger Domänen.
15. [Aktivieren Skype for Business Hybrid zwischen](configure-federation-with-skype-for-business-online.md) lokalen AcquiredCompany. <span> com und die Cloud.
16. Migrieren Sie die Benutzer wie gewünscht [von der lokalen in die Cloud.](move-users-between-on-premises-and-cloud.md) Sie können Benutzer entweder direkt in den [TeamsOnly-Modus](/microsoftteams/teams-and-skypeforbusiness-coexistence-and-interoperability) migrieren oder sie zuerst zu Skype for Business Online migrieren. Während dieses Zustands sieht die Organisation wie **[Abbildung D aus.](#figure-d)**
17. Nachdem alle Benutzer migriert wurden, deaktivieren Sie [die Hybridumgebung](cloud-consolidation-disabling-hybrid.md) mit der lokalen Umgebung, um die Organisation zur reinen *Cloud zu machen.*

Die folgenden Diagramme zeigen die Konfiguration an verschiedenen wichtigen Punkten während dieses Prozesses.

##### <a name="figure-a"></a>Abbildung A:

- Beide Organisationen werden über AAD Verbinden synchronisiert, sodass AAD nun alle Benutzer aus beiden lokalen Bereitstellungen hat.
- Alle Benutzer werden lokal heimgeheimt.  
- Skype for Business Hybrid ist *noch* nicht konfiguriert.
- Wenn Benutzer in beiden Bereitstellungen Teams verwenden, können sie keine Zusammenarbeit (oder eine Organisation) und auch keine Interoperabilität mit Skype for Business haben. In dieser Phase empfiehlt Microsoft, nur Teams Kanäle zu verwenden.<br><br>
    ![Abbildung Ein Diagramm](../media/cloudconsolidationfiga.png)

##### <a name="figure-b"></a>Abbildung B:

- AcquiredCompany. <span> com ist eine [deaktivierte Online-SIP-Domäne.](/powershell/module/skype/disable-csonlinesipdomain) Alle Benutzer sind lokal. Wenn sie Teams sie keinen Verbund oder keine Interoperabilität haben. In dieser Phase empfiehlt Microsoft, nur Teams Kanäle zu verwenden.
- Skype for Business Hybrid wurde für eine der lokalen Organisationen aktiviert.
- Einige Benutzer in der Hybridorganisation wurden in die Cloud verschoben (Benutzer A, wie durch lila Schattierung angegeben). Diese Benutzer können entweder Skype for Business Onlinebenutzer oder Teams Nur Benutzer mit vollständiger Interoperabilität und Verbundunterstützung sein.<br><br>
    ![Abbildung B-Diagramm](../media/cloudconsolidationfigb.png)

##### <a name="figure-c"></a>Abbildung C:

- Alle Benutzer von OriginalCompany. <span> com befinden sich jetzt in der Cloud (in Skype for Business Online). Es wird empfohlen, dass sie auch nur Teams werden.
- Skype for Business hybride Konfiguration mit der OriginalCompany. <span> die Com-Bereitstellung wurde deaktiviert. Die lokale Bereitstellung ist weg.
- Wenn AcquiredCompany. <span> com war zuvor nicht mit AAD synchronisiert, um von hier aus fortfahren zu können, muss es jetzt synchronisiert werden. Sie ist jedoch noch nicht hybrid (freigegebener SIP-Adressraum), und bis die Organisation bereit ist, zu hybrid zu wechseln, sollte die Online-SIP-Domäne für die reine lokale Organisation (AcquiredCompany.com) deaktiviert bleiben, damit Online-Teams-Benutzer mit lokalen Benutzern kommunizieren können.<br><br>
    ![Abbildung C-Diagramm](../media/cloudconsolidationfigc.png)

##### <a name="figure-d"></a>Abbildung D:

- AcquiredCompany. <span> com ist jetzt als Online-SIP-Domäne aktiviert.
- Lokal wird aktualisiert, um OriginalCompany zu akzeptieren. <span> com. (Sowohl zulässige Domänen- als auch Edgezertifikate werden aktualisiert).
- Der freigegebene SIP-Adressraum ist zwischen AcquiredCompany aktiviert. <span> com und Microsoft 365 oder Office 365 Organisation.
- Einige Benutzer in der Hybridorganisation wurden möglicherweise in die Cloud verschoben, z. B. Benutzer D unten (angezeigt durch lila Schattierung).<br><br>
    ![Abbildung D-Diagramm](../media/cloudconsolidationfigd.png)

## <a name="other-starting-points"></a>Andere Ausgangspunkte

In den schritten im obigen kanonischen Beispiel wird davon ausgegangen, dass die Organisation mit zwei lokalen Verbundbereitstellungen ohne Microsoft oder Office 365 beginnt. Einige Organisationen verfügen jedoch möglicherweise über einen vorhandenen Microsoft 365 oder Office 365, und es können unterschiedliche Einstiegspunkte in die obige Sequenz vorhanden sein. Es gibt vier typische Konfigurationen:

- Mehrere lokale Partnerorganisationen ohne Microsoft 365 oder Office 365 Organisation. Beginnen Sie in diesem Fall mit Schritt 1.
- Mehrere lokale Verbundorganisationen, die bereits mehrere Skype for Business mit einem einzelnen Azure AD-Mandanten synchronisieren. Eine solche Organisation ähnelt der hypothetischen Organisation in Abbildung A, die die Schritte 1 bis 6 abgeschlossen hat und mit Schritt 7 beginnen sollte.
- Eine Hybridorganisation, die mit einer oder mehreren anderen reinen lokalen Organisationen zusammenarbeiten, von denen keine mit AAD synchronisiert wird. Eine solche Organisation ähnelt der hypothetischen Organisation in **Abbildung E**, siehe unten.
    - Diese Organisation ähnelt Abbildung B, die die Schritte 1 bis 9 abgeschlossen hat, außer:
        - Die Nichthybridbereitstellungen Skype for Business noch *NICHT* mit Azure AD synchronisiert.
        -  Online-SIP-Domänen sind noch nicht deaktiviert. 
    - Diese Organisationen sollten entweder:
        - Schließen Sie die Migration der vorhandenen Hybridorganisation ab, und geben Sie die obige Sequenz in Schritt 10 ein.  OR,
        - Wenn es gewünscht ist, alle anderen Skype for Business-Gesamtstrukturen vor abschluss der Migration der Hybridorganisation mit AAD zu synchronisieren, muss die Organisation Schritt 7 ausführen (alle Online-SIP-Domänen in jeder anderen lokalen Skype for Business-Bereitstellung deaktivieren, die mit AAD synchronisiert wird) und dann AAD Verbinden aktivieren und dann nur mit Schritt 10 fortfahren (die ursprüngliche Hybridbereitstellung außer Betrieb setzen).       
                **Abbildung E**<br>
                ![Abbildung E-Diagramm](../media/cloudconsolidationfige.png)
- Eine reine Skype for Business -Online-Organisation (die möglicherweise Teams verwendet), die mit einer separaten lokalen Organisation Skype for Business wird. Sobald diese Organisation die #A0 für die lokale Organisation deaktiviert und AAD Verbinden für die lokale Skype for Business-Organisation aktiviert hat, ähnelt sie der hypothetischen Organisation in Abbildung **[C,](#figure-c)** die die Schritte 1 bis 11 abgeschlossen hat.

## <a name="limitations"></a>Einschränkungen

- Es muss in der Organisation Microsoft 365 oder Office 365 sein. Die Konsolidierung in Szenarien mit mehreren Organisationen wird nicht unterstützt.
- Nur eine lokale Skype for Business kann sich gleichzeitig im Hybridmodus (freigegebener SIP-Adressraum) befinden. Alle anderen lokalen Skype for Business müssen rein lokal bleiben und sollten miteinander und der organisation Microsoft 365 oder Office 365 werden.
- Vor der Migration in die Cloud gibt es in dieser Bereitstellung eine asymmetrische Benutzererfahrung, da nicht alle Onlinebenutzer lokal dargestellt werden:
    - Die Erfahrung kann wie folgt zusammengefasst werden:
        - Jeder Onlinebenutzer interagiert mit lokalen Benutzern in der Hybridumgebung, als wäre der Benutzer hybrid.
        - Lokale Benutzer in der Hybridbereitstellung interagieren mit Onlinebenutzern, die in ihrem lokalen Verzeichnis so dargestellt werden, als wären sie Hybridbenutzer. 
        - Lokale Benutzer in der Hybridbereitstellung interagieren mit Onlinebenutzern, die nicht in lokalem AD als Verbund dargestellt sind.
    - In **[Abbildung D](#figure-d)** oben ist Benutzer E in AcquiredCompany lokal. <span> com.  Benutzer E interagiert mit Benutzer D (online) mithilfe der standardmäßigen Hybriderfahrung, Benutzer E verfügt jedoch über eine Verbunderfahrung mit den Benutzern A, B und C, da sie nicht im lokalen Verzeichnis dargestellt werden. Die Benutzer A, B und C interagieren jedoch mit Benutzer E, als wäre der Benutzer hybrid.
    - Auswirkungen der Interaktion im Vergleich zum Verbund:
        - Anwesenheit wird für Verbundbenutzer nicht automatisch abonniert, es sei denn, der Benutzer ist als Kontakt gekennzeichnet.
        - Die Anruf weiterleitung funktioniert nicht zwischen Verbunddomänen.
        - Anrufübertragungsszenarien sind eingeschränkter.
        - Drosselung kann auf Verbunddatenverkehr angewendet werden.
- Angesichts dieser asymmetrischen Erfahrung ist die offizielle Unterstützung für das Aufrufen von Funktionen in standortübergreifenden Szenarien zwischen einem lokalen Und einem Cloudbenutzer, der sich nicht im lokalen Verzeichnis befindet, auf Peers beschränkt. 
    - Die Weiterleitung von Anrufen, Übertragungen, Anrufwarteschlangen usw. zwischen diesen Benutzern wird nicht unterstützt.
    - Diese nicht unterstützten Anrufszenarien werden weiterhin aktiviert angezeigt, in vielen Fällen treten jedoch unvorhersehbare Fehler auf. 
    - In **[Abbildung D](#figure-d)** oben ist Benutzer E lokal, und Anrufe mit den Benutzern A, B oder C werden nur als Peer zu Peer unterstützt. (Anrufe mit Benutzer D hätten keine Supporteinschränkungen.)  Nachdem der lokale Benutzer E in die Cloud verschoben wurde, gilt diese Einschränkung jedoch nicht mehr.
- Wenn Sie über mehr als eine Bereitstellung von Skype for Business Server 2019 in Ihrer Umgebung verfügen, kann nur 1 dieser Bereitstellung für die Verwendung von Organizational automatische Telefonzentrale konfiguriert werden, da für dieses Feature eine Skype for Business Server erforderlich ist. 
- Die Reihenfolge einiger der vorherigen Schritte kann angepasst werden. Die wichtigste Anforderung, die erfüllt werden muss, ist, dass, wenn alle diese erfüllt sind:
    - Mehr als ein lokales Skype for Business mit einem einzelnen AAD-Mandanten
    - Geteilte Domäne ist mit einer lokalen Gesamtstruktur aktiviert
    - Mindestens ein Benutzer in der Hybridorganisation wurde in die Cloud migriert.<br>   Anschließend müssen Sie *alle anderen* Online-SIP-Domänen von allen anderen lokalen Domänen Skype for Business deaktivieren. Andernfalls bricht der Verbund zwischen Onlinebenutzern in der Hybridorganisation und lokalen Benutzern in anderen Organisationen in eine Richtung.

## <a name="implications"></a>Implikationen

- Da es Einschränkungen bei der Unterstützung erweiterter Anruffunktionen gibt, wie oben beschrieben, sollten Organisationen diese asymmetrischen Zustände im Rahmen der Migration als transitorisch behandeln und nicht als stabilen **Status verfolgen.**  
- Organisationen mit mehreren lokalen Skype for Business sollten im Allgemeinen mit einer Bereitstellung beginnen, die vollständig in die Cloud migriert werden kann, damit die Konsolidierung fortgesetzt werden kann. Es wird verstanden, dass es in einigen Fällen Halteschleifen bestimmter Benutzergruppen gibt, für die es noch nicht praktikabel ist, zu Teams. Wenn dies in Szenarien mit mehreren Gesamtstrukturen Skype for Business, beginnen Sie mit der Migration mit einer anderen Gesamtstruktur, die diese Einschränkungen nach Möglichkeit nicht hat.
- Beim Wechsel von der lokalen in die Cloud sollten Benutzer, die delegierungsbeziehungen haben und/oder in der Regel an Anruf weiterleitungsszenarien beteiligt sind, als Einheit verschoben werden.

## <a name="considerations-for-moving-to-teamsonly-mode"></a>Überlegungen zum Wechseln in den TeamsOnly-Modus

Wenn Sie Benutzer in einer Hybridumgebung von lokal in die Cloud verschieben, können Sie sie entweder in den Skype for Business oder den TeamsOnly-Modus verschieben. *Wenn Sie planen, Benutzer in den TeamsOnly-Modus zu verschieben, lesen Sie diesen Abschnitt zuerst.*

- Wenn Sie einem Benutzer den TeamsOnly-Modus zuweisen, landen alle Chats und Anrufe eines anderen Benutzers im Teams des Benutzers. 
- Wenn Benutzer mit Skype for Business lokalen Benutzern hauptsächlich Skype for Business-Client und nicht Teams verwenden, sollten Sie TeamsUpgradePolicy so festlegen, dass das Routing zu diesen lokalen Benutzern immer in Skype for Business anstatt in Teams. Um ein ordnungsgemäßes Routing von Chats und Anrufen zwischen Benutzern zu gewährleisten, die TeamsOnly sind, und Benutzern, die weiterhin Skype for Business lokal verwenden, müssen lokale Benutzer einen effektiven Wert von TeamsUpgradePolicy mit einem der SfB-Modi anstelle von Inseln (standard) haben. 
    - Hierzu müssen Sie zunächst die globale Instanz Ihres Mandanten *von TeamsUpgradePolicy* auf einen der folgenden Werte festlegen:
        - SfBWithTeamsCollab (empfohlen)
        - SfBWithTeamsCollabAndMeetings
        - SfBOnly
    - Sie können eine mandantenweite Richtlinie mithilfe des folgenden Befehls erteilen:<br>`Grant-CsTeamsUpgradePolicy -PolicyName SfBWithTeamsCollab -Global`
    - Hinweis: Sie müssen dies auf mandantenweitem Niveau tun, da Richtlinien nicht einzelnen Benutzern zugewiesen werden können, die nicht über eine SIP-Adresse im Onlineverzeichnis verfügen. Während Sie Online-SIP-Domänen für Ihre reinen lokalen Bereitstellungen deaktiviert haben, verfügen Benutzer in diesen Domänen nicht standardmäßig über SIP-Adressen im Onlineverzeichnis. Daher besteht die einzige Möglichkeit zum Anwenden von Richtlinien auf diese lokalen Benutzer in der Zuweisung auf Mandantenebene. Im Gegensatz dazu haben Benutzer in der Hybridbereitstellung eine SIP-Adresse im Onlineverzeichnis, sodass ihnen explizit eine Richtlinie zugewiesen werden kann, wenn gewünscht wird, dass sie einen anderen Wert als die globale Mandantenrichtlinie haben.
- Die Teams-Client-UX berücksichtigt noch nicht die SfB-Modi von TeamsUpgradePolicy. Wenn beispielsweise in diesen Modi die Anruf- und Chatinitiierung in Teams ist derzeit möglich, auch wenn dies in Zukunft nicht der Fall sein wird. Dies kann zu Verwirrung unter den Benutzern führen, da Antworten je nach den Umständen manchmal Teams und manchmal Skype for Business werden. Es wird empfohlen, Anrufe und Chats über TeamsMessagingPolicy und TeamsCallingPolicy für Benutzer, die sich noch lokal befinden, separat zu deaktivieren.

## <a name="see-also"></a>Siehe auch

[Aktualisieren des Edgezertifikats](cloud-consolidation-edge-certificates.md)

[Aktualisieren von AAD Connect, um mehrere Gesamtstrukturen einzuschließen](cloud-consolidation-aad-connect.md)

[Deaktivieren der Hybridbereitstellung zur Durchführung der Migration in die Cloud](cloud-consolidation-disabling-hybrid.md)