---
title: Cloud-Konsolidierung für Teams und Skype for Business
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
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
description: In diesem Artikel wird beschrieben, wie Sie eine Konsolidierung für Organisationen mit lokalen Bereitstellungen von Skype for Business (oder lync) erreichen können, die ihre UC-Arbeitsauslastung in Microsoft Teams und/oder Skype for Business Online umsetzen möchten.
ms.openlocfilehash: 46e84f9a65ec7626c5285196af83d63baa46c15e
ms.sourcegitcommit: a78fee3cad5b58bf41dd014a79f4316cf310c8d1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/29/2019
ms.locfileid: "36160604"
---
# <a name="cloud-consolidation-for-teams-and-skype-for-business"></a>Cloud-Konsolidierung für Teams und Skype for Business

Viele große Unternehmen verfügen über mehr als eine lokale AD-Gesamtstruktur, und in einigen Fällen verfügen Kunden über mehr als eine Exchange-und/oder Skype for Business Server-(oder lync Server-) Bereitstellung. Darüber hinaus könnten sich Selbstorganisationen mit nur einer lokalen Gesamtstruktur über eine Unternehmenszusammenführung oder-Akquisition in einer ähnlichen Situation befinden. Wenn diese Kunden in die Cloud umziehen, möchten Sie die mehrere Instanzen einer bestimmten lokalen Arbeitsauslastung in der Cloud in einem einzigen Office 365 Mandanten konsolidieren. In diesem Artikel wird beschrieben, wie Sie diese Konsolidierung für Organisationen mit mehreren lokalen Bereitstellungen von Skype for Business (oder lync) erreichen, die ihre UC-Arbeitsauslastung in die Microsoft-Cloud umstellen möchten, beispielsweise Microsoft Teams und/oder Skype for Business Online.

In der Vergangenheit war es für Kunden in dieser Situation hilfreich, die Bereitstellungen zunächst lokal zusammenzufassen und dann in die Cloud zu migrieren. Dies ist zwar weiterhin eine Option, aber in diesem Artikel wird eine Lösung beschrieben, die auf neuen Funktionen basiert, mit denen Organisationen mit mehreren Skype for Business-Bereitstellungen jeweils eine Bereitstellung zu einem einzelnen Office 365-Mandanten migrieren können, ohne lokale Konsolidierung. Beachten Sie, dass Skype for Business Online und Microsoft Teams selbst mit dieser neuen Funktionalität nicht mehrere Skype for Business/lync-Gesamtstrukturen im Hybrid Modus mit einem einzelnen Office 365 Mandanten unterstützen. 

> [!Important]
> Bevor Sie dieses Handbuch für die Konfiguration verwenden, sollten Sie die [Einschränkungen](#limitations)überprüfen und verstehen, die sich auf Ihre Organisation auswirken können.

## <a name="overview-of-cloud-consolidation"></a>Übersicht über die Cloud-Konsolidierung

Die Konsolidierung aller Benutzer von lokal in der Cloud in einem einzelnen Office 365 Mandanten kann für jede Organisation mit mehreren Skype for Business-Bereitstellungen erreicht werden, vorausgesetzt, die folgenden Hauptanforderungen werden erfüllt:

- Es muss höchstens ein Office 365-Mandanten beteiligt sein. Die Konsolidierung in Szenarien mit mehr als einem Office 365 Mandanten wird nicht unterstützt.
- Zu einem bestimmten Zeitpunkt kann sich nur eine lokale Skype for Business Gesamtstruktur im Hybrid Modus befinden (freigegebener SIP-Adressraum). Alle anderen lokalen Skype for Business Gesamtstrukturen müssen lokal (und vermutlich miteinander verbunden) bleiben. Beachten Sie, dass diese anderen lokalen Organisationen ** mit Aad, falls gewünscht, mit [neuen Funktionen synchronisiert werden können, um Online-SIP-Domänen zu deaktivieren](https://docs.microsoft.com/en-us/powershell/module/skype/disable-csonlinesipdomain?view=skype-ps) , die ab Dezember 2018 verfügbar sind.

Kunden mit Bereitstellungen von Skype for Business in mehreren Gesamtstrukturen müssen alle Benutzer einer einzelnen Hybriden Skype for Business Gesamtstruktur einzeln in den Office 365 Mandanten mit freigegebener SIP-Adressraum Funktionalität migrieren und anschließend die hybridbereitstellung mit diesem deaktivieren. lokale Bereitstellung, bevor Sie fortfahren, um die nächste lokale Skype for Business-Bereitstellung zu migrieren. Vor der Migration in die Cloud verbleiben lokale Benutzer in einem Verbund Status mit allen Benutzern, die nicht im lokalen Verzeichnis des Benutzers dargestellt werden.  

## <a name="canonical-example-of-cloud-consolidation"></a>Kanonisches Beispiel für die Cloud-Konsolidierung

Stellen Sie sich eine Organisation mit zwei getrennten Verbund lokalen Bereitstellungen von Skype for Business vor, die Sie online in Microsoft Teams oder Skype for Business Online konsolidieren möchten.


|Original Statusdetails |Details zum gewünschten Zustand |
|---------|---------|
|<ul><li>2 unabhängige Skype for Business lokale Bereitstellungen in getrennten AD-Gesamtstrukturen<li>Höchstens 1 Gesamtstruktur ist in Hybrid mit Skype for Business Online <li> Organisationen sind miteinander verbunden. <li>Benutzer werden nicht über diese Gesamtstrukturen synchronisiert.<li> Die Organisation hat möglicherweise einen Office 365 Mandanten und synchronisiert möglicherweise Ihr Verzeichnis in Azure AD</ul>|<ul> <li>1 Office 365 Mandant<li>Keine weiteren lokalen Bereitstellungen, sodass keine Hybriden verbleiben<li>Alle Benutzer von lokal werden in Skype for Business Online verwaltet und können optional nur Teams-Benutzer sein. <li>Keine lokale Grundfläche von Skype for Business Anywhere <li>Benutzer verfügen weiterhin über eine lokale Authentifizierung</ul> |

![Konsolidieren von zwei separaten Verbund lokalen Bereitstellungen](../media/cloudconsolidationfig1.png)  

Die grundlegenden Schritte, die vom ursprünglichen Zustand zum gewünschten Endzustand gelangen, sind unten.  Beachten Sie, dass einige Organisationen möglicherweise feststellen, dass Ihr Ausgangspunkt irgendwo in der Mitte dieser Schritte liegt. [Weitere Startpunkte](#other-starting-points)finden Sie weiter unten in diesem Artikel. Schließlich kann in einigen Fällen die Reihenfolge angepasst werden, je nach Bedarf. [Wichtige Einschränkungen und Einschränkungen](#limitations) werden später beschrieben.

1.  Dient zum Abrufen eines Office 365 Mandanten, falls noch nicht vorhanden.
2.  Stellen Sie sicher, dass alle relevanten SIP-Domänen in beiden lokalen Bereitstellungen Office 365 Domänen überprüft werden.
3.  Wählen Sie eine Skype for Business Bereitstellung aus, die mit Office 365 Hybrid ist. In diesem Beispiel verwenden wir OriginalCompany. <span>com.
4.  [Aktivieren Sie Aad Connect für die Gesamtstruktur](configure-azure-ad-connect.md) , die zuerst als Hybrid verwendet<span> wird (OriginalCompany. com). 
5.  Wenn Sie Microsoft Teams in Ihrer Organisation einführen, legen Sie die Mandantenweite Richtlinie für [TeamsUpgradePolicy](https://docs.microsoft.com/en-us/powershell/module/skype/grant-csteamsupgradepolicy) auf SfBWithTeamsCollab oder einen der anderen SFB-Modi fest (SfBOnly oder SfBWithTeamsCollabAndMeetings). Dies ist wichtig, um sicherzustellen, dass Anrufe und Chats von Benutzern, die nur zu Microsoft Teams übergehen, an Benutzer weitergeleitet werden, die lokal verbleiben.
6.  Es wird zu diesem Zeitpunkt empfohlen (aber bis Schritt 11 noch nicht erforderlich), um [Aad Connect für die andere Gesamtstruktur](cloud-consolidation-aad-connect.md) zu aktivieren<span> (AcquiredCompany. com). Unter der Voraussetzung, dass Aad Connect in beiden Gesamtstrukturen aktiviert ist, sieht die org aus wie in **[Abbildung a](#figure-a)**, was ein häufiger Ausgangspunkt für einige Organisationen sein kann. 
7.  Für alle SIP-Domänen, die von anderen lokalen Bereitstellungen gehostet werden (in diesem Fall AcquiredCompany<span> . com), [Deaktivieren Sie diese SIP-Domänen in Skype for Business Online](https://docs.microsoft.com/en-us/powershell/module/skype/disable-csonlinesipdomain) mithilfe `Disable-CsOnlineSipDomain` von in PowerShell. (Dies ist die neue Funktionalität vom Dezember 2018.)
8.  [Konfigurieren Sie Skype for Business Hybrid](configure-federation-with-skype-for-business-online.md) für OriginalCompany. <span>com (die einzige Bereitstellung, die Online-SIP-Domänen noch aktiviert hat).
9.  In der hybridbereitstellung (OriginalCompany.<span> com), beginnen [Sie mit dem Verschieben von Benutzern aus Skype for Business lokal in die Cloud](move-users-between-on-premises-and-cloud.md) (unabhängig davon, ob es sich um Teams handelt oder nicht), sodass das Konto in Skype for Business Online verwaltet wird. Die Organisation sieht nun wie in **[Abbildung B](#figure-b)** aus. Die wichtigsten Änderungen aus Abbildung A sind:
    - Benutzer aus lokalen Verzeichnissen befinden sich jetzt in Aad.
    - AcquiredCompany. <span>com ist eine deaktivierte Online-SIP-Domäne.
    - Einige Benutzer wurden online in Skype for Business Online oder Teams verschoben. (Siehe Purple User A.)
10. Nachdem alle Benutzer in die Cloud verschoben wurden, [Deaktivieren Sie Hybrid mit der Skype for Business lokalen Bereitstellung](cloud-consolidation-disabling-hybrid.md) für OriginalCompany. <span>com aus Office 365:  
    - Deaktivieren Sie die geteilte Domäne im Office 365 Mandanten.
    - Deaktivieren Sie die Möglichkeit zur Kommunikation mit Office 365 in OriginalCompany. <span>com lokal.
    - Aktualisieren von DNS-Einträgen für OriginalCompany. <span>com, um auf Office 365 zu deuten.
11. Wenn dies noch nicht geschehen ist, [Aktivieren Sie Aad Connect für die nächste Gesamtstruktur](cloud-consolidation-aad-connect.md) , die Hybrid<span> wird (AcquiredCompany. com). Zu diesem Zeitpunkt sieht die Organisation wie **[Abbildung C](#figure-c)** aus. Dies kann ein weiterer häufiger Ausgangspunkt für einige Organisationen sein. 
12. Aktivieren Sie in PowerShell [die SIP-Domänen für die nächste lokale Bereitstellung](https://docs.microsoft.com/en-us/powershell/module/skype/enable-csonlinesipdomain?view=skype-ps) , die als Hybrid-AcquiredCompany verwendet wird. <span>com. Dies erfolgt über `Enable-CsOnlineSipDomain`die neue Funktionalität ab Dezember 2018.
13. Wenn Sie einen geschlossenen Partnerverbund verwenden, müssen Sie alle SIP-Domänen (ausgenommen *. microsoftonline.com) des reinen Online-Mandanten als zugelassene Domänen in **derselben** Office 365 hinzufügen. Beachten Sie, dass es einige Zeit dauern kann, bis die Änderung wirksam wird, und es ist nicht möglich, dies frühzeitig zu tun, daher empfehlen wir, dies rechtzeitig vor dem Wechsel zu Schritt 14 zu tun.
14. Aktualisieren Sie die lokale Umgebung, um SIP-Domänen vom Online Mandanten zu akzeptieren, damit diese übereinstimmen.
    - [Aktualisieren Sie das San in allen Edge-Zertifikaten](cloud-consolidation-edge-certificates.md) auf den gleichen Wert wie zuvor, plus Werte für alle vorhandenen Online-SIP-Domänen (außer *. microsoftonline.com), in diesem Fall SIP. OriginalCompany. <span>com.
    - Stellen Sie sicher, dass OriginalCompany. <span>com ist eine [zugelassene Domäne](https://docs.microsoft.com/en-us/powershell/module/skype/new-csalloweddomain) in der lokalen Bereitstellung, AcquiredCompany. Hinzufügen zulässiger Domänen.
15. [Aktivieren Sie Skype for Business Hybrid](configure-federation-with-skype-for-business-online.md) zwischen lokalen AcquiredCompany. <span>com und die Cloud.
16. [Migrieren Sie nach Bedarf Benutzer von der lokalen zur Cloud](move-users-between-on-premises-and-cloud.md). Sie können Benutzer entweder direkt in den [TeamsOnly](/microsoftteams/teams-and-skypeforbusiness-coexistence-and-interoperability) -Modus migrieren, oder Sie können Sie zuerst zu Skype for Business Online migrieren. In diesem Zustand sieht die Organisation wie in **[Abbildung D](#figure-d)** aus.
17. Nachdem alle Benutzer migriert wurden, [Deaktivieren Sie Hybrid mit der lokalen Umgebung](cloud-consolidation-disabling-hybrid.md) , um *die Organisation als reine Cloud zu gestalten*.

Die folgenden Diagramme zeigen die Konfiguration an verschiedenen wichtigen Punkten während dieses Prozesses.

##### <a name="figure-a"></a>Abbildung A:

- Beide Organisationen werden über Aad Connect synchronisiert, sodass Aad jetzt über alle Benutzer aus lokalen Bereitstellungen verfügt.
- Alle Benutzer, die lokal verwaltet werden.  
- Skype for Business-Hybrid ist noch *nicht* konfiguriert.
- Wenn Benutzer in einer der Bereitstellungen Microsoft Teams verwenden, können Sie nicht miteinander (oder einer Organisation) einen Partnerverbund haben und keine Interoperabilität mit Skype for Business Benutzern haben. In dieser Phase empfiehlt Microsoft die Verwendung von Teams nur für Kanäle.<br><br>
    ![Abbildung eines Diagramms](../media/cloudconsolidationfiga.png)

##### <a name="figure-b"></a>Abbildung B:

- AcquiredCompany. <span>com ist eine [](https://docs.microsoft.com/en-us/powershell/module/skype/disable-csonlinesipdomain) deaktivierte Online-SIP-Domäne. Alle Benutzer sind lokal. Wenn Sie Teams verwenden, haben Sie keinen Verbund oder keine Interoperabilität. In dieser Phase empfiehlt Microsoft die Verwendung von Teams nur für Kanäle.
- Skype for Business Hybrid wurde für eine der lokalen Organisationen aktiviert.
- Einige Benutzer in der Hybrid Organisation wurden in die Cloud verschoben (Benutzer A wird durch violette Schattierung angezeigt). Diese Benutzer können entweder Skype for Business Online Benutzer oder nur Microsoft Teams-Benutzer mit vollständiger Interoperabilität und Verbundunterstützung sein.<br><br>
    ![Abbildung B-Diagramm](../media/cloudconsolidationfigb.png)

##### <a name="figure-c"></a>Abbildung C:

- Alle Benutzer aus OriginalCompany. <span>com befinden sich jetzt in der Cloud (in Skype for Business Online verwaltet). Es wird empfohlen, dass es sich auch um Teams handelt.
- Skype for Business Hybrid Konfiguration mit dem OriginalCompany. <span>die com-Bereitstellung wurde deaktiviert. Die lokale Bereitstellung ist nicht mehr vorhanden.
- Wenn AcquiredCompany. <span>com wurde nicht zuvor mit Aad synchronisiert, um von hier fortfahren zu können, muss jetzt synchronisiert werden. Die Online-SIP-Domäne für die reine lokale Organisation (AcquiredCompany.com) sollte jedoch noch nicht als Hybrid (freigegebener SIP-Adressraum) verwendet werden, und bis die Organisation bereit ist, zu einer hybridbereitstellung zu übergehen, sollten die Benutzer in Online Teams mit lokale Benutzer.<br><br>
    ![Abbildung C Diagramm](../media/cloudconsolidationfigc.png)

##### <a name="figure-d"></a>Abbildung D:

- AcquiredCompany. <span>com ist jetzt als Online-SIP-Domäne aktiviert.
- Lokal wird aktualisiert, um OriginalCompany zu akzeptieren. <span>com. (Sowohl zulässige Domäne als auch Edge-Zertifikate werden aktualisiert).
- Der freigegebene SIP-Adressraum ist zwischen AcquiredCompany aktiviert. <span>com und Office 365 Mandanten.
- Einige Benutzer in der Hybrid Organisation wurden möglicherweise in die Cloud verschoben, wie z. b. Benutzer D unten (durch violette Schattierung angegeben).<br><br>
    ![Abbildung D-Diagramm](../media/cloudconsolidationfigd.png)

## <a name="other-starting-points"></a>Andere Ausgangspunkte

In den Schritten im kanonischen Beispiel wird davon ausgegangen, dass die Organisation mit zwei lokalen Verbund Bereitstellungen ohne Office 365 Anwesenheit beginnt. Einige Organisationen haben jedoch möglicherweise einen vorhandenen Office 365 Footprint, und es kann unterschiedliche Einstiegspunkte in der obigen Sequenz geben. Es gibt vier typische Konfigurationen:

- Mehrere lokale Verbundorganisationen ohne Office 365 Mandanten. Beginnen Sie in diesem Fall mit Schritt 1.
- Mehrere lokale Verbundorganisationen, die bereits mehrere Skype for Business Gesamtstruktur mit einem einzelnen Azure AD-Mandanten synchronisieren. Eine solche Organisation ähnelt der hypothetischen Organisation in Abbildung A, die die Schritte 1-6 abgeschlossen hat und mit Schritt 7 beginnen sollte.
- Eine Hybrid Organisation, die mit mindestens einer anderen reinen lokalen Organisation zusammenhängt, von denen keine mit Aad synchronisiert wird. Eine solche Organisation würde der hypothetischen Organisation in **Abbildung E**ähneln, siehe unten.
    - Diese Organisation ähnelt Abbildung B, die die Schritte 1-9 abgeschlossen hat, mit Ausnahme von:
        - Die nicht Hybriden Skype for Business-Bereitstellungen werden noch *nicht* mit Azure AD synchronisiert.
        -  Online-SIP-Domänen sind noch nicht deaktiviert. 
    - Diese Organisationen sollten entweder:
        - Führen Sie die Migration der vorhandenen Hybrid Organisation aus, und geben Sie die obige Sequenz in Schritt 10 ein.  Oder
        - Wenn eine andere Skype for Business Gesamtstruktur in Aad vor Abschluss der Migration der Hybrid Organisation synchronisiert werden soll, muss die Organisation Schritt 7 ausführen (deaktivieren Sie alle Online-SIP-Domänen in einer anderen lokalen Skype for Business-Bereitstellung, die Synchronisieren Sie mit AAD), und aktivieren Sie dann Aad Connect, und fahren Sie dann mit Schritt 10 fort (außer Betrieb der ursprünglichen hybridbereitstellung).       
                **Abbildung E**<br>
                ![Abbildung E Diagramm](../media/cloudconsolidationfige.png)
- Eine reine Skype for Business Online Organisation (die möglicherweise Teams verwendet oder nicht), die mit einer separaten lokalen Skype for Business Organisation zusammenarbeitet. Sobald diese Organisation die Online-SIP-Domäne für die lokale Organisation deaktiviert und Aad Connect für die lokale Skype for Business Organisation aktiviert, ähnelt Sie der in **[Abbildung C](#figure-c)** dargestellten hypothetischen Organisation mit den abgeschlossenen Schritten. 1-11.

## <a name="limitations"></a>Einschränkungen

- Es muss höchstens ein Office 365-Mandanten beteiligt sein. Die Konsolidierung in Szenarien mit mehr als einem Office 365 Mandanten wird nicht unterstützt.
- Nur eine lokale Skype for Business Gesamtstruktur kann sich im Hybrid Modus (freigegebener SIP-Adressraum) gleichzeitig befinden. Alle anderen lokalen Skype for Business Gesamtstrukturen müssen nur lokal bleiben und miteinander und mit dem Office 365 Mandanten verbunden sein.
- Vor der Migration zur Cloud gibt es für Benutzer in dieser Bereitstellung eine asymmetrische Erfahrung, da nicht alle Benutzer in Online lokal dargestellt werden:
    - Die Erfahrung lässt sich wie folgt zusammenfassen:
        - Jeder Benutzer, der Online verwaltet wird, interagiert mit lokalen Benutzern in der Hybridumgebung, als wäre der Benutzer Hybrid.
        - Lokale Benutzer in der hybridbereitstellung interagieren mit Online Benutzern, die in Ihrem lokalen Verzeichnis dargestellt werden, als wären Sie Hybrid. 
        - Lokale Benutzer in der hybridbereitstellung interagieren mit Online Benutzern, die nicht im lokalen AD als Verbund dargestellt werden.
    - In **[Abbildung D](#figure-d)** ist der Benutzer E lokal in AcquiredCompany. <span>com.  Benutzer e interagiert mit dem Benutzer D (verwaltet Online) mit der standardmäßigen Hybridumgebung, aber Benutzer e verfügt über eine Verbund Erfahrung mit den Benutzern a, B und C, da Sie nicht im lokalen Verzeichnis dargestellt werden. Die Benutzer A, B und C interagieren jedoch mit dem Benutzer E so, als ob sich der Benutzer in einer hybridbereitstellung befinden würde.
    - Auswirkungen der Interaktion als hybrides vs. Federation:
        - Anwesenheitsinformationen werden für Partnerbenutzer nicht automatisch abonniert, es sei denn, der Benutzer ist als Kontakt markiert.
        - Die Anrufweiterleitung kann zwischen Verbunddomänen nicht verwendet werden.
        - Die Anruf Übertragungs Szenarien sind geringer.
        - Einschränkung kann auf Verbunddatenverkehr angewendet werden.
- Aufgrund dieser asymmetrischen Erfahrung ist die offizielle Unterstützung für das Aufrufen von Funktionen in standortübergreifenden Szenarien zwischen einem lokalen Benutzer und einem Cloud-Benutzer, der sich nicht im lokalen Verzeichnis befindet, nur auf Peer-to-Peer beschränkt. 
    - Anrufweiterleitung, Übertragung, Anrufwarteschlangen, etc. zwischen diesen Benutzern wird nicht unterstützt.
    - Diese nicht unterstützten Anrufszenarien werden weiterhin aktiviert angezeigt, in vielen Fällen werden Sie jedoch auf unvorhersehbare Weise fehlschlagen. 
    - In **[Abbildung D](#figure-d)** ist der Benutzer E lokal, und Anrufe mit den Benutzern A, B oder C werden nur als Peer-to-Peer unterstützt. (Anrufe mit Benutzer D würden keine Supporteinschränkungen haben.)  Wenn der lokale Benutzer E jedoch in die Cloud verschoben wird, gilt diese Einschränkung nicht mehr.
- Wenn Sie mehr als eine Bereitstellung von Skype for Business Server 2019 in Ihrer Umgebung haben, kann nur 1 dieser Bereitstellung für die Verwendung der automatischen Telefonzentrale konfiguriert werden, da für dieses Feature Skype for Business Server Hybrid Konfiguration erforderlich ist. 
- Die Reihenfolge der vorherigen Schritte kann angepasst werden. Die Hauptanforderung muss erfüllt sein, wenn alle diese zutreffen:
    - Mehr als eine lokale Skype for Business Gesamtstruktur, die mit einem einzelnen Aad-Mandanten synchronisiert wird
    - Die geteilte Domäne ist mit einer lokalen Gesamtstruktur aktiviert.
    - Mindestens ein Benutzer in der Hybrid Organisation wurde in die Cloud migriert.<br>   Anschließend *müssen* Sie alle anderen SIP-Online Domänen in einer anderen lokalen Skype for Business Gesamtstruktur deaktivieren. Andernfalls wird der Verbund zwischen Online Benutzern in der Hybrid Organisation und lokalen Benutzern in anderen Organisationen in eine Richtung unterbrechen.

## <a name="implications"></a>Auswirkungen

- Da die Unterstützung für erweiterte Anruffunktionen wie oben beschrieben eingeschränkt ist, **sollten Organisationen diese asymmetrischen Zustände als vorübergehend im Rahmen der Migration behandeln und nicht als Steady-State verfolgen**.  
- Organisationen mit mehreren lokalen Skype for Business-Bereitstellungen sollten im Allgemeinen mit einer Bereitstellung beginnen, die vollständig in die Cloud migriert werden kann, damit die Konsolidierung fortgesetzt werden kann. Es wird davon ausgegangen, dass in einigen Fällen Verweigerer bestimmter Benutzergruppen vorhanden sein werden, für die es noch Nichtlebens fähig ist, zu Microsoft Teams zu gelangen. Wenn dies in Szenarien mit mehreren Skype for Business Gesamtstrukturen berücksichtigt wird, beginnen Sie, wenn möglich, mit einer anderen Gesamtstruktur zu migrieren, die diese Einschränkungen nicht aufweist.
- Beim Wechsel von der lokalen in die Cloud sollten Benutzer, die über Delegierungs Beziehungen verfügen und/oder normalerweise an Anruf Weiterleitungs Szenarien beteiligt sind, als Einheit zusammen verschoben werden.

## <a name="considerations-for-moving-to-teamsonly-mode"></a>Überlegungen zum Verschieben in den TeamsOnly-Modus

Wenn Sie Benutzer in einer Hybridumgebung von lokal in die Cloud migrieren, können Sie Sie in Skype for Business oder in den TeamsOnly-Modus versetzen. *Wenn Sie beabsichtigen, die Benutzer in den TeamsOnly-Modus zu versetzen, lesen Sie diesen Abschnitt zuerst.*

- Wenn Sie einem Benutzer den TeamsOnly-Modus zuweisen, werden alle Chats und Anrufe von anderen Benutzern in den Microsoft Teams-Client des Benutzers gelandet. 
- Um eine ordnungsgemäße Weiterleitung von Chats und anrufen zwischen Benutzern, die TeamsOnly sind, und Benutzern, die noch Skype for Business lokal verwenden, sicherzustellen, müssen Sie sicherstellen, dass lokale Benutzer über einen der SFB-Modi TeamsUpgradePolicy, statt auf Inseln (standardmäßig ). 
    - Hierzu *müssen Sie zuerst die globale Instanz von TeamsUpgradePolicy des Mandanten auf einen der folgenden Werte festlegen*:
        - SfBWithTeamsCollab (empfohlen)
        - SfBWithTeamsCollabAndMeetings
        - SfBOnly
    - Sie können eine Mandantenweite Richtlinie mithilfe dieses Befehls erteilen:<br>`Grant-CsTeamsUpgradePolicy -PolicyName SfBWithTeamsCollab -Global`
    - Hinweis: derzeit müssen Sie dies auf einer Mandanten weiten Ebene tun, da Richtlinien nicht einzelnen Benutzern zugewiesen werden können, die keine SIP-Adresse im Online Verzeichnis haben. Während Sie Online-SIP-Domänen für Ihre reinen lokalen Bereitstellungen deaktiviert haben, haben Benutzer in diesen Domänen keine SIP-Adressen im Online-Verzeichnis nach Design. Die einzige Möglichkeit, Richtlinien auf diese lokalen Benutzer anzuwenden, ist daher die Zuweisung auf Mandantenebene. Im Gegensatz dazu verfügen Benutzer in der hybridbereitstellung über eine SIP-Adresse im Online Verzeichnis, sodass Ihnen eine Richtlinie explizit zugewiesen werden kann, wenn Sie einen anderen Wert als die globale Mandanten Richtlinie haben soll.
- Der Client-UX von Teams ehrt die SFB-Modi von TeamsUpgradePolicy noch nicht. Wenn in diesen Modi beispielsweise die Initiierung von Anrufen und Chats in Microsoft Teams derzeit möglich ist, ist dies in Zukunft nicht der Fall. Dies kann zu Verwechslungen zwischen Benutzern führen, da Antworten manchmal in Teams und manchmal Skype for Business, je nach den jeweiligen Umständen, landen können. Es wird empfohlen, dass Sie Anrufe und Chats über TeamsMessagingPolicy und TeamsCallingPolicy für Benutzer, die sich weiterhin lokal befinden, separat deaktivieren.

## <a name="see-also"></a>Siehe auch

[Aktualisieren des Edge-Zertifikats](cloud-consolidation-edge-certificates.md)

[Aktualisieren von Aad Connect, um mehr als eine Gesamtstruktur einzubeziehen](cloud-consolidation-aad-connect.md)

[Deaktivieren der hybridbereitstellung zur vollständigen Migration in die Cloud](cloud-consolidation-disabling-hybrid.md)
