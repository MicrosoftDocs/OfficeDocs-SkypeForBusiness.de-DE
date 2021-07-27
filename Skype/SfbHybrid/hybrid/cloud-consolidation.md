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
description: In diesem Artikel wird beschrieben, wie Sie diese Konsolidierung für Organisationen mit lokalen Bereitstellungen von Skype for Business (oder Lync) erreichen, die ihre UC-Workload auf Teams und/oder Skype for Business Online verschieben möchten.
ms.openlocfilehash: 6a6d433be8b6be5519f1bf7576464603e29ee41b
ms.sourcegitcommit: 9879bc587382755d9a5cd63a75b0e7dc4e15574c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/21/2021
ms.locfileid: "53510726"
---
# <a name="cloud-consolidation-for-teams-and-skype-for-business"></a>Cloudkonsolidierung für Microsoft Teams und Skype for Business

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]


Viele Großunternehmen verfügen über mehr als eine lokale AD-Gesamtstruktur, und in einigen Fällen verfügen Kunden über mehr als eine Bereitstellung von Exchange und/oder Skype for Business Server (oder Lync Server). Darüber hinaus können sich auch Organisationen mit nur einer lokalen Gesamtstruktur bei einer Fusion oder Übernahme in einer ähnlichen Situation befinden. Wenn diese Kunden in die Cloud wechseln, möchten sie die mehreren Instanzen einer bestimmten lokalen Workload in der Cloud in einer einzigen Microsoft 365 oder Office 365 Organisation konsolidieren. In diesem Artikel wird beschrieben, wie Sie diese Konsolidierung für Organisationen mit mehreren lokalen Bereitstellungen von Skype for Business (oder Lync) erreichen, die ihre UC-Workload in die Microsoft-Cloud verschieben möchten, z. B. Microsoft Teams und/oder Skype for Business Online.

[!INCLUDE [sfbo-retirement-skype](../../Hub/includes/sfbo-retirement.md)]

In der Vergangenheit war es für Kunden in dieser Situation so, dass sie Bereitstellungen zuerst lokal konsolidieren mussten und erst dann einen Umstieg in die Cloud vollziehen konnten. Obwohl dies immer noch eine Option ist, wird in diesem Artikel eine Lösung beschrieben, die auf neuen Funktionen basiert, mit denen Organisationen mit mehreren Skype for Business Bereitstellungen eine Bereitstellung nach der anderen in eine einzelne Microsoft 365 oder Office 365 Organisation migrieren können, ohne eine lokale Konsolidierung durchzuführen. Beachten Sie, dass auch bei dieser neuen Funktion Skype for Business Online- und Microsoft Teams nicht mehrere Skype for Business/Lync-Gesamtstrukturen im Hybridmodus mit einer einzelnen Microsoft 365 oder Office 365 Organisation unterstützen. 

> [!Important]
> Bevor Sie dieses Handbuch für die Konfiguration verwenden, sollten Sie die [Einschränkungen](#limitations)überprüfen und verstehen, da sie sich auf Ihre Organisation auswirken können.

## <a name="overview-of-cloud-consolidation"></a>Übersicht über die Cloudkonsolidierung

Die Konsolidierung aller Benutzer aus der lokalen Umgebung in die Cloud in einer einzigen Microsoft 365 oder Office 365 Organisation kann für jede Organisation mit mehreren Skype for Business Bereitstellungen erreicht werden, vorausgesetzt, die folgenden wichtigen Anforderungen sind erfüllt:

- Es muss mindestens eine Microsoft 365 oder Office 365 Organisation beteiligt sein. Die Konsolidierung in Szenarien mit mehr als einer Organisation wird nicht unterstützt.
- Es darf jeweils nur eine lokale Skype for Business-Gesamtstruktur im Hybridmodus (freigegebener SIP-Adressraum) vorhanden sein. Alle anderen lokalen Skype for Business-Gesamtstrukturen müssen lokal bleiben (und vermutlich miteinander verbunden sein). Beachten Sie, dass diese anderen lokalen Organisationen bei Bedarf mit AAD synchronisiert *werden können,* um die ab Dezember 2018 verfügbaren [Online-SIP-Domänen zu deaktivieren.](/powershell/module/skype/disable-csonlinesipdomain)

Kunden mit Bereitstellungen von Skype for Business in mehreren Gesamtstrukturen müssen alle Benutzer einer einzelnen Hybrid-Skype for Business-Gesamtstruktur einzeln in die Microsoft 365 oder Office 365 Organisation migrieren, indem sie die Funktionalität des freigegebenen SIP-Adressraums verwenden, und dann die Hybridbereitstellung mit dieser lokalen Bereitstellung deaktivieren, bevor sie die nächste lokale Skype for Business Bereitstellung migrieren. Vor der Migration in die Cloud verbleiben lokale Benutzer in einem Verbundstatus mit allen Benutzern, die nicht im lokalen Verzeichnis des gleichen Benutzers dargestellt sind.  

## <a name="canonical-example-of-cloud-consolidation"></a>Kanonisches Beispiel für die Cloudkonsolidierung

Betrachten Sie eine Organisation mit zwei separaten lokalen Verbundbereitstellungen von Skype for Business, die sie online in Microsoft Teams oder Skype for Business Online konsolidieren möchten.


|Ursprüngliche Statusdetails |Gewünschte Statusdetails |
|---------|---------|
|<ul><li>2 unabhängige Skype for Business lokalen Bereitstellungen in separaten AD-Gesamtstrukturen<li>Höchstens 1 Gesamtstruktur befindet sich in einer Hybridumgebung mit Skype for Business Online <li> Organisationen sind miteinander verbunden <li>Benutzer werden in diesen Gesamtstrukturen nicht synchronisiert<li> Die Organisation verfügt möglicherweise über eine Microsoft 365 oder Office 365 Organisation und synchronisiert möglicherweise ihr Verzeichnis mit Azure AD.</ul>|<ul> <li>1 Microsoft 365 oder Office 365 Organisation<li>Keine lokalen Bereitstellungen mehr, daher bleibt keine Hybridbereitstellung übrig<li>Alle Lokalen Benutzer werden in Skype for Business Online verwaltet und können optional nur Teams Benutzer sein. <li>Kein lokaler Speicherbedarf von Skype for Business an beliebiger Stelle <li>Benutzer verfügen weiterhin über lokale Authentifizierung</ul> |

![Konsolidieren von zwei separaten lokalen Verbundbereitstellungen](../media/cloudconsolidationfig1.png)  

Die grundlegenden Schritte, um vom ursprünglichen Zustand zum gewünschten Endzustand zu gelangen, finden Sie unten.  Beachten Sie, dass einige Organisationen möglicherweise feststellen, dass sich ihr Ausgangspunkt irgendwo in der Mitte dieser Schritte befindet. Weitere [Startpunkte](#other-starting-points)finden Sie weiter unten in diesem Artikel. Schließlich kann die Reihenfolge in einigen Fällen je nach Bedarf angepasst werden. [Wichtige Einschränkungen und Einschränkungen](#limitations) werden später beschrieben.

1.  Rufen Sie eine Microsoft 365 oder Office 365 Organisation ab, falls noch keine vorhanden ist.
2.  Stellen Sie sicher, dass alle relevanten SIP-Domänen in beiden lokalen Bereitstellungen Microsoft 365 oder Office 365 Domänen überprüft werden.
3.  Wählen Sie eine Skype for Business Bereitstellung aus, die hybrid mit Microsoft 365 oder Office 365 sein soll. In diesem Beispiel verwenden wir OriginalCompany. <span> Com.
4.  [Aktivieren Sie AAD-Verbinden für die Gesamtstruktur,](configure-azure-ad-connect.md) die zuerst hybrid wird (OriginalCompany. <span> com). 
5.  Wenn Sie Teams in Ihre Organisation einführen, legen Sie die mandantenweite Richtlinie für [TeamsUpgradePolicy](/powershell/module/skype/grant-csteamsupgradepolicy) auf SfBWithTeamsCollab oder einen der anderen SfB-Modi (SfBOnly oder SfBWithTeamsCollabAndMeetings) fest. Dies ist wichtig, um das Routing von Anrufen und Chats von Benutzern, die zu Teams nur zu Benutzern wechseln, die lokal bleiben, sicherzustellen.
6.  Es wird empfohlen, zu diesem Zeitpunkt (aber noch nicht erforderlich bis Schritt 11) [AAD-Verbinden für die andere Gesamtstruktur](cloud-consolidation-aad-connect.md) (AcquiredCompany) zu aktivieren. <span> com). Wenn AAD Verbinden in beiden Gesamtstrukturen aktiviert ist, sieht die Organisation wie **[in Abbildung A](#figure-a)** aus, was für einige Organisationen ein gemeinsamer Ausgangspunkt sein kann. 
7.  Für alle SIP-Domänen, die von anderen lokalen Bereitstellungen gehostet werden (in diesem Fall AcquiredCompany. <span> com), [deaktivieren Sie diese SIP-Domänen in Skype for Business Online](/powershell/module/skype/disable-csonlinesipdomain) mithilfe von `Disable-CsOnlineSipDomain` PowerShell. (Dies ist eine neue Funktion seit Dezember 2018.)
8.  [Konfigurieren Sie Skype for Business Hybrid](configure-federation-with-skype-for-business-online.md) für OriginalCompany. <span> [com](configure-federation-with-skype-for-business-online.md) (die Bereitstellung, die weiterhin Online-SIP-Domänen aktiviert hat).
9.  In der Hybridbereitstellung (OriginalCompany. <span> beginnen Sie mit [dem Verschieben von Benutzern von Skype for Business lokal in die Cloud](move-users-between-on-premises-and-cloud.md) (ob nur Teams oder nicht), damit das Konto in Skype for Business Online verwaltet wird. Jetzt sieht die Organisation wie **[in Abbildung B](#figure-b)** aus. Die wichtigsten Änderungen in Abbildung A sind:
    - Benutzer aus beiden lokalen Verzeichnissen befinden sich jetzt in AAD.
    - AcquiredCompany. <span> com ist eine deaktivierte Online-SIP-Domäne.
    - Einige Benutzer wurden entweder in Skype for Business Online oder Teams online verschoben. (Siehe lila Benutzer A.)
10. Sobald alle Benutzer in die Cloud verschoben wurden, [deaktivieren Sie die Hybridbereitstellung mit der Skype for Business lokalen Bereitstellung](cloud-consolidation-disabling-hybrid.md) für OriginalCompany. <span> com von Office 365:  
    - Deaktivieren Sie die geteilte Domäne in der Microsoft 365 oder Office 365 Organisation.
    - Deaktivieren Sie die Möglichkeit, mit Microsoft 365 oder Office 365 in OriginalCompany zu kommunizieren. <span> com lokal.
    - Aktualisieren sie DNS-Einträge für OriginalCompany. <span> com, um auf Microsoft 365 oder Office 365 zu verweisen.
11. Wenn dies noch nicht geschehen ist, [aktivieren Sie AAD-Verbinden für die nächste Gesamtstruktur,](cloud-consolidation-aad-connect.md) die hybrid wird (AcquiredCompany. <span> com). An diesem Punkt sieht die Organisation wie **[in Abbildung C](#figure-c)** aus. Dies kann ein weiterer gängiger Ausgangspunkt für einige Organisationen sein. 
12. Aktivieren Sie in PowerShell [die SIP-Domänen für die nächste lokale Bereitstellung,](/powershell/module/skype/enable-csonlinesipdomain) die als Hybridbereitstellung verwendet wird: AcquiredCompany. <span> Com. Dies erfolgt mithilfe `Enable-CsOnlineSipDomain` der neuen Funktion, die ab Dezember 2018 verfügbar ist.
13. Wenn Sie einen geschlossenen Partnerverbund verwenden, müssen Sie alle SIP-Domänen (mit Ausnahme \* von .microsoftonline.com) des reinen Onlinemandanten als zulässige Domänen in **derselben** Microsoft 365 oder Office 365 hinzufügen. Beachten Sie, dass es einige Zeit dauern kann, bis die Änderung wirksam wird, und es keinen Schaden an dieser frühen Vorgehensweise gibt. Daher empfehlen wir, dies rechtzeitig vor dem Übergang zu Schritt 14 zu tun.
14. Aktualisieren Sie die lokale Umgebung so, dass sip-Domänen vom Onlinemandanten akzeptiert werden, damit sie übereinstimmen.
    - [Aktualisieren Sie den SAN in allen Edgezertifikaten](cloud-consolidation-edge-certificates.md) auf den gleichen Wert wie zuvor sowie die Werte für alle vorhandenen Online-SIP-Domänen (außer *.microsoftonline.com), in diesem Fall Sip.OriginalCompany. <span> Com.
    - Stellen Sie sicher, dass OriginalCompany. <span> com ist eine [zulässige Domäne](/powershell/module/skype/new-csalloweddomain) in der lokalen Bereitstellung, AcquiredCompany. Fügen Sie zulässige Domänen hinzu.
15. [Aktivieren Sie Skype for Business Hybridlösung](configure-federation-with-skype-for-business-online.md) zwischen der lokalen AcquiredCompany. <span> com und der Cloud.
16. Migrieren Sie nach Bedarf [Benutzer aus der lokalen Umgebung in die Cloud.](move-users-between-on-premises-and-cloud.md) Sie können Benutzer entweder direkt in den [TeamsOnly-Modus](/microsoftteams/teams-and-skypeforbusiness-coexistence-and-interoperability) oder zuerst zu Skype for Business Online migrieren. In diesem Zustand sieht die Organisation wie **[in Abbildung D](#figure-d)** aus.
17. Nachdem alle Benutzer migriert wurden, [deaktivieren Sie die Hybridbereitstellung mit der lokalen Umgebung,](cloud-consolidation-disabling-hybrid.md) um die Organisation zu einer *reinen Cloud* zu machen!

Die folgenden Diagramme zeigen die Konfiguration während dieses Prozesses an verschiedenen Wichtigen Punkten.

##### <a name="figure-a"></a>Abbildung A:

- Beide Organisationen werden über AAD Verbinden synchronisiert, sodass AAD jetzt alle Benutzer aus beiden lokalen Bereitstellungen hat.
- Alle Benutzer, die lokal verwaltet werden.  
- Skype for Business Hybrid ist noch *nicht* konfiguriert.
- Wenn Benutzer in beiden Bereitstellungen Teams verwenden, können sie sich nicht miteinander (oder mit einer Organisation) verbinden, und sie verfügen auch nicht über Interoperabilität mit Skype for Business Benutzern. In dieser Phase empfiehlt Microsoft die Verwendung von Teams nur für Kanäle.<br><br>
    ![Abbildung Eines Diagramms](../media/cloudconsolidationfiga.png)

##### <a name="figure-b"></a>Abbildung B:

- AcquiredCompany. <span> com ist eine [deaktivierte](/powershell/module/skype/disable-csonlinesipdomain) Online-SIP-Domäne. Alle Benutzer sind lokal. Wenn sie Teams verwenden, verfügen sie über keinen Partnerverbund oder keine Interoperabilität. In dieser Phase empfiehlt Microsoft die Verwendung von Teams nur für Kanäle.
- Skype for Business Hybrid wurde für eine der lokalen Organisationen aktiviert.
- Einige Benutzer in der Hybridorganisation wurden in die Cloud verschoben (Benutzer A, wie durch lila Schattierung angegeben). Diese Benutzer können entweder Skype for Business Onlinebenutzer oder Teams Nur Benutzer mit vollständiger Interoperabilität und Verbundunterstützung sein.<br><br>
    ![Abbildung B-Diagramm](../media/cloudconsolidationfigb.png)

##### <a name="figure-c"></a>Abbildung C:

- Alle Benutzer von OriginalCompany. <span> com sind jetzt in der Cloud (verwaltet in Skype for Business Online). Es wird empfohlen, dass sie auch Teams only sind.
- Skype for Business Hybridkonfiguration mit der OriginalCompany. <span> Die Com-Bereitstellung wurde deaktiviert. Die lokale Bereitstellung ist nicht mehr vorhanden.
- Wenn AcquiredCompany. <span> com wurde zuvor nicht mit AAD synchronisiert, um von hier aus fortzufahren, muss es jetzt synchronisiert werden. Aber es ist noch nicht hybrid (freigegebener SIP-Adressraum), und bis die Organisation bereit ist, zur Hybridbereitstellung zu wechseln, sollte die Online-SIP-Domäne für die reine lokale Organisation (AcquiredCompany.com) deaktiviert bleiben, damit Online-Teams Benutzer mit lokalen Benutzern kommunizieren können.<br><br>
    ![Abbildung C-Diagramm](../media/cloudconsolidationfigc.png)

##### <a name="figure-d"></a>Abbildung D:

- AcquiredCompany. <span> com ist jetzt als Online-SIP-Domäne aktiviert.
- Lokal wird aktualisiert, um OriginalCompany zu akzeptieren. <span> Com. (Sowohl zulässige Domänenzertifikate als auch Edgezertifikate werden aktualisiert).
- Der freigegebene SIP-Adressraum ist zwischen AcquiredCompany aktiviert. <span> com und Microsoft 365 oder Office 365 Organisation.
- Einige Benutzer in der Hybridorganisation wurden möglicherweise in die Cloud verschoben, z. B. Benutzer D unten (durch lila Schattierung gekennzeichnet).<br><br>
    ![Abbildung D-Diagramm](../media/cloudconsolidationfigd.png)

## <a name="other-starting-points"></a>Andere Ausgangspunkte

Bei den Schritten im obigen kanonischen Beispiel wird davon ausgegangen, dass die Organisation mit zwei lokalen Verbundbereitstellungen ohne Microsoft oder Office 365 Auftritt beginnt. Einige Organisationen verfügen jedoch möglicherweise über einen vorhandenen Microsoft 365- oder Office 365-Fußabdruck, und es können unterschiedliche Einstiegspunkte in der obigen Sequenz vorhanden sein. Es gibt vier typische Konfigurationen:

- Mehrere lokale Verbundorganisationen ohne Microsoft 365 oder Office 365 Organisation. Beginnen Sie in diesem Fall mit Schritt 1.
- Mehrere lokale Verbundorganisationen, die bereits mehrere Skype for Business Gesamtstruktur mit einem einzelnen Azure AD-Mandanten synchronisieren. Eine solche Organisation ähnelt der hypothetischen Organisation in Abbildung A, die die Schritte 1 bis 6 abgeschlossen hat und mit Schritt 7 beginnen sollte.
- Eine Hybridorganisation, die mit 1 oder mehr reinen lokalen Organisationen verbunden ist, von denen keine mit AAD synchronisiert wird. Eine solche Organisation würde der hypothetischen Organisation in **Abbildung E** ähneln , wie unten dargestellt.
    - Diese Organisation ist vergleichbar mit Abbildung B, in der die Schritte 1 bis 9 ausgeführt wurden, mit Ausnahme der folgenden:
        - Die nicht hybriden Skype for Business Bereitstellungen werden noch *NICHT* mit Azure AD synchronisiert.
        -  Online-SIP-Domänen sind noch nicht deaktiviert. 
    - Diese Organisationen sollten folgende Aktionen ausführen:
        - Führen Sie die Migration der vorhandenen Hybridorganisation durch, und geben Sie die oben genannte Sequenz in Schritt 10 ein.  Oder
        - Wenn vor Abschluss der Migration der Hybridorganisation andere Skype for Business Gesamtstrukturen mit AAD synchronisiert werden sollen, muss die Organisation Schritt 7 ausführen (alle Online-SIP-Domänen in allen anderen lokalen Skype for Business-Bereitstellungen deaktivieren, die mit AAD synchronisiert werden) und dann AAD Verbinden aktivieren und erst dann mit Schritt 10 fortfahren (Außerbetriebnahme der ursprünglichen Hybridbereitstellung).       
                **Abbildung E**<br>
                ![Abbildung E-Diagramm](../media/cloudconsolidationfige.png)
- Eine reine Skype for Business Onlineorganisation (die möglicherweise Teams verwendet), die mit einer separaten lokalen Skype for Business Organisation verbunden ist. Sobald diese Organisation die Online-SIP-Domäne für die lokale Organisation deaktiviert und AAD-Verbinden für die lokale Skype for Business Organisation aktiviert hat, ähnelt sie der hypothetischen Organisation in **[Abbildung C,](#figure-c)** die die Schritte 1 bis 11 abgeschlossen hat.

## <a name="limitations"></a>Einschränkungen

- Es muss mindestens eine Microsoft 365 oder Office 365 Organisation beteiligt sein. Die Konsolidierung in Szenarien mit mehr als einer Organisation wird nicht unterstützt.
- Nur eine lokale Skype for Business Gesamtstruktur kann sich jeweils im Hybridmodus (freigegebener SIP-Adressraum) befinden. Alle anderen lokalen Skype for Business Gesamtstrukturen müssen ausschließlich lokal bleiben und miteinander und der Microsoft 365 oder Office 365 Organisation verbunden sein.
- Vor der Migration in die Cloud gibt es eine asymmetrische Erfahrung für Benutzer in dieser Bereitstellung, da nicht alle Benutzer in der Onlineumgebung lokal dargestellt werden:
    - Die Erfahrung kann wie folgt zusammengefasst werden:
        - Jeder Onlinebenutzer interagiert mit lokalen Benutzern in der Hybridumgebung, als wäre der Benutzer hybrid.
        - Lokale Benutzer in der Hybridbereitstellung interagieren mit Onlinebenutzern, die in ihrem lokalen Verzeichnis dargestellt werden, als wären sie hybrid. 
        - Lokale Benutzer in der Hybridbereitstellung interagieren mit Onlinebenutzern, die nicht im lokalen AD als Verbund dargestellt sind.
    - In **[Abbildung D](#figure-d)** oben ist Benutzer E lokal in AcquiredCompany. <span> Com.  Benutzer E interagiert mit Benutzer D (online verwaltet) mithilfe der Standardhybridumgebung, benutzer E verfügt jedoch über eine Verbunderfahrung mit den Benutzern A, B und C, da sie nicht im lokalen Verzeichnis dargestellt werden. Die Benutzer A, B und C interagieren jedoch mit Benutzer E, als ob sich der Benutzer in einer Hybridumgebung bef?t.
    - Auswirkungen der Interaktion im Vergleich zum Hybridverbund:
        - Anwesenheit wird nicht automatisch für Verbundbenutzer abonniert, es sei denn, der Benutzer ist als Kontakt gekennzeichnet.
        - Die Anrufweiterleitung funktioniert nicht zwischen Verbunddomänen.
        - Anrufübertragungsszenarien sind begrenzter.
        - Drosselung kann auf Verbunddatenverkehr angewendet werden.
- Aufgrund dieser asymmetrischen Erfahrung ist die offizielle Unterstützung für Anruffunktionen in standortübergreifenden Szenarien zwischen einem lokalen Benutzer und einem Cloudbenutzer, der sich nicht im lokalen Verzeichnis befindet, auf Peer-to-Peer beschränkt. 
    - Anrufweiterleitung, -übertragung, Anrufwarteschleifen usw. zwischen diesen Benutzern werden nicht unterstützt.
    - Diese nicht unterstützten Anrufszenarien werden weiterhin aktiviert angezeigt, in vielen Fällen treten jedoch unvorhersehbare Fehler auf. 
    - In **[Abbildung D](#figure-d)** oben ist Benutzer E lokal, und Anrufe mit Benutzern A, B oder C werden nur als Peer-to-Peer unterstützt. (Anrufe mit Benutzer D haben keine Supporteinschränkungen.)  Nachdem der lokale Benutzer E jedoch in die Cloud verschoben wurde, gilt diese Einschränkung nicht mehr.
- Wenn Sie mehr als eine Bereitstellung von Skype for Business Server 2019 in Ihrer Umgebung haben, kann nur 1 dieser Bereitstellungen für die Verwendung der automatischen Telefonzentrale der Organisation konfiguriert werden, da für dieses Feature Skype for Business Server Hybridkonfiguration erforderlich ist. 
- Die Reihenfolge einiger der vorherigen Schritte kann angepasst werden. Die wichtigste Anforderung, die erfüllt werden muss, ist Folgendes, wenn alle diese erfüllt sind:
    - Mehrere lokale Skype for Business Gesamtstruktur, die mit einem einzelnen AAD-Mandanten synchronisiert werden
    - Geteilte Domäne ist mit einer lokalen Gesamtstruktur aktiviert
    - Mindestens ein Benutzer in der Hybridorganisation wurde in die Cloud migriert.<br>   Anschließend *müssen* Sie alle anderen Online-SIP-Domänen aus allen anderen lokalen Skype for Business Gesamtstruktur deaktivieren. Andernfalls wird der Verbund zwischen Onlinebenutzern in der Hybridorganisation und lokalen Benutzern in anderen Organisationen in eine Richtung aufgehoben.

## <a name="implications"></a>Auswirkungen

- Da es Einschränkungen bei der Unterstützung erweiterter Anruffunktionen wie oben beschrieben gibt, **sollten Organisationen diese asymmetrischen Zustände im Rahmen der Migration als vorübergehend behandeln und nicht als stabilen Zustand verfolgen.**  
- Organisationen mit mehreren lokalen Skype for Business Bereitstellungen sollten in der Regel mit einer Bereitstellung beginnen, die vollständig in die Cloud migriert werden kann, damit die Konsolidierung fortgesetzt werden kann. Es wird davon ausgegangen, dass in einigen Fällen bestimmte Benutzergruppen gehalten werden, für die es noch nicht möglich ist, zu Teams zu wechseln. Wenn dies in Szenarien mit mehreren Skype for Business Gesamtstrukturen berücksichtigt wird, beginnen Sie, wenn möglich, mit einer anderen Gesamtstruktur zu migrieren, die diese Einschränkungen nicht aufweist.
- Wenn Sie von der lokalen Bereitstellung in die Cloud wechseln, sollten Benutzer, die Delegierungsbeziehungen haben und/oder in der Regel an Anrufweiterleitungsszenarien beteiligt sind, als Einheit zusammen verschoben werden.

## <a name="considerations-for-moving-to-teamsonly-mode"></a>Überlegungen für den Wechsel in den TeamsOnly-Modus

Wenn Sie Benutzer in einer Hybridumgebung von der lokalen Umgebung in die Cloud verschieben, können Sie sie entweder in Skype for Business Only- oder TeamsOnly-Modus verschieben. *Wenn Sie beabsichtigen, Benutzer in den TeamsOnly-Modus zu verschieben, lesen Sie zuerst diesen Abschnitt.*

- Wenn Sie einem Benutzer den TeamsOnly-Modus zuweisen, landen alle Chats und Anrufe eines anderen Benutzers im Teams Client dieses Benutzers. 
- Wenn Benutzer mit Skype for Business lokalen Bereitstellung in erster Linie Skype for Business Client und nicht Teams verwenden, sollten Sie teamsUpgradePolicy so festlegen, dass das Routing zu diesen lokalen Benutzern immer in Skype for Business statt in Teams erfolgt. Um eine ordnungsgemäße Weiterleitung von Chats und Anrufen zwischen Benutzern, bei denen es sich um TeamsOnly handelt, und Benutzern, die weiterhin Skype for Business lokal verwenden, sicherzustellen, müssen lokale Benutzer einen effektiven Wert von TeamsUpgradePolicy mit einem der SfB-Modi anstelle von Inseln haben (dies ist der Standardwert). 
    - Dazu müssen Sie zunächst die *globale Instanz von TeamsUpgradePolicy Ihres Mandanten auf einen der folgenden Werte festlegen:*
        - SfBWithTeamsCollab (empfohlen)
        - SfBWithTeamsCollabAndMeetings
        - SfBOnly
    - Mit diesem Befehl können Sie mandantenweite Richtlinien erteilen:<br>`Grant-CsTeamsUpgradePolicy -PolicyName SfBWithTeamsCollab -Global`
    - Hinweis: Sie müssen dies auf mandantenweiter Ebene tun, da die Richtlinie nicht einzelnen Benutzern zugewiesen werden kann, die keine SIP-Adresse im Onlineverzeichnis haben. Während Sie Online-SIP-Domänen für Ihre reinen lokalen Bereitstellungen deaktiviert haben, verfügen Benutzer in diesen Domänen entwurfsbedingt nicht über SIP-Adressen im Onlineverzeichnis. Daher besteht die einzige Möglichkeit zum Anwenden von Richtlinien auf diese lokalen Benutzer darin, sie auf Mandantenebene zuzuweisen. Im Gegensatz dazu verfügen Benutzer in der Hybridbereitstellung über eine SIP-Adresse im Onlineverzeichnis, sodass ihnen explizit eine Richtlinie zugewiesen werden kann, wenn sie einen anderen Wert als die globale Mandantenrichtlinie haben möchten.
- Die Teams Client-UX berücksichtigt noch nicht die SfB-Modi von TeamsUpgradePolicy. Wenn z. B. in diesen Modi Anruf- und Chatinitiierung in Teams derzeit möglich ist, wird dies in Zukunft jedoch nicht der Fall sein. Dies kann zu Verwirrung bei den Benutzern führen, da Antworten je nach Den Umständen manchmal in Teams und manchmal Skype for Business landen können. Es wird empfohlen, Anrufe und Chats über TeamsMessagingPolicy und TeamsCallingPolicy für Benutzer, die sich noch lokal befinden, separat zu deaktivieren.

## <a name="see-also"></a>Mehr dazu

[Aktualisieren des Edgezertifikats](cloud-consolidation-edge-certificates.md)

[Aktualisieren von AAD Connect, um mehrere Gesamtstrukturen einzuschließen](cloud-consolidation-aad-connect.md)

[Deaktivieren der Hybridbereitstellung zur Durchführung der Migration in die Cloud](cloud-consolidation-disabling-hybrid.md)