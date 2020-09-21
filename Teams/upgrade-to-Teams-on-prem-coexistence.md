---
title: Koexistenz mit Microsoft Teams und Skype for Business
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 09/16/20
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: bjwhalen
description: Upgrade von Skype for Business auf Teams-Koexistenz
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- NOCSH
ms.custom: Teams-upgrade-guidance
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 2c5993611a383ee9b7040dfa4b74dae1b392253f
ms.sourcegitcommit: b37632ffa22e3a6045b476c95d46889e9193a15b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/17/2020
ms.locfileid: "47955962"
---
# <a name="coexistence-with-teams-and-skype-for-business"></a>Koexistenz mit Teams und Skype for Business

In diesem Artikel werden die Verhaltensweisen zusammengefasst, die beim Ausführen von Teams und Skype for Business-Clients in derselben Organisation auftreten können, unabhängig davon, in welchem Modus und welche Aktualisierungsmethode verwendet wird:

- [Besprechungen](#meetings)
- [Interoperabilität](#interoperability)
- [Teams-Unterhaltungen – Interop versus native Threads](#teams-conversations---interop-versus-native-threads)
- [Anwesenheit](#presence)
- [Partnerverbund](#federation)
- [Kontakte](#contacts)



## <a name="meetings"></a>Besprechungen

Unabhängig von Ihrem Modus können Benutzer immer an jeder Art von Besprechung teilnehmen, zu der Sie eingeladen werden, egal ob es sich um Skype for Business oder Teams handelt.  Benutzer müssen jedoch an der Besprechung mit einem entsprechenden Clientteil nehmen, der dem Besprechungstyp entspricht:

- Wenn es sich bei der Besprechung um eine Teambesprechung handelt, verwenden alle Teilnehmer (ob TeamsOnly, Inseln oder Skype for Business-Benutzer) den Team-Client, um an der Besprechung teilzunehmen. Wenn Teams nicht installiert ist, wird der Benutzer beim Versuch, an einer Besprechung teilzunehmen, an das Internet weitergeleitet.

- Wenn es sich bei der Besprechung um eine Skype for Business-Besprechung handelt, verwenden alle Teilnehmer (ob TeamsOnly, Inseln oder Skype for Business-Benutzer) den Skype for Business-Client, um an der Besprechung teilzunehmen. Wenn der Skype for Business-Client nicht installiert ist, wird der Benutzer an das Web weitergeleitet, um über die Skype-Besprechungs-App teilnehmen zu können.

Beim Organisieren von Besprechungen basiert der Besprechungstyp, der geplant wird, auf dem Modus des Organisators, wie in der folgenden Tabelle dargestellt:

| Modus von Organizer    |      Verhalten |
| :------------------ | :---------------- |
| TeamsOnly, SfbWithTeamsCollabAndMeetings |    Alle in Teams geplanten Besprechungen Das Skype for Business-Add-in steht in Outlook nicht zur Verfügung. | 
| SfbWithTeamsCollab, SfbOnly   | Alle in Skype for Business geplanten Besprechungen Das Team-Add-in steht in Outlook nicht zur Verfügung. | 
| Inselmodus | Standardmäßig können Besprechungen entweder in Skype for Business oder in Teams geplant werden. Beide Add-Ins stehen in Outlook zur Verfügung. Sie können jedoch optional festlegen, dass Benutzer auf Inseln Besprechungen in Teams immer planen, indem Sie Ihnen eine Instanz von TeamsMeetingPolicy mit dem PreferredMeetingProviderForIslandsMode = Teams zuweisen.| 


## <a name="interoperability"></a>Interoperabilität

Teams unterstützt Interoperabilität ("Interop") mit Skype for Business in bestimmten Szenarien. Die Interop-Kommunikation bezieht sich auf einen Chat oder einen Anruf zwischen einem Skype for Business-Benutzer und einem Teams-Benutzer.  Die Interop-Kommunikation ist nur zwischen zwei Benutzern möglich. mehr Parteien-Chat/-Anrufe oder das Hinzufügen weiterer Benutzer werden nicht unterstützt.

Ein Interop-Chat oder-Anruf zwischen zwei Benutzern wird erstellt, wenn jede der folgenden Bedingungen zutrifft:

- Ein Benutzer verwendet Teams, und der andere Nutzer nutzt Skype for Business.

- Der Modus des Empfängers der anfänglichen Kommunikation ist keine Inseln (andernfalls würde die Kommunikation in demselben Client landen), wenn sich beide Benutzer in derselben Organisation befinden. In Verbundszenarien verwendet der sendende Benutzer Teams, und der Empfänger befindet sich nicht im TeamsOnly-Modus. 

- Der Benutzer des Teams hat nicht auch ein Skype for Business-Konto, das lokal verwaltet wird. 

In der Interop-Kommunikation ist Chat nur mit nur-Text-Funktion. Darüber hinaus sind Dateifreigabe und Bildschirmübertragung *im Interop-Chat selbst*nicht möglich. Benutzer in einer Interop-Unterhaltung können jedoch problemlos Datei-und/oder Bildschirm Freigaben erreichen, indem Sie im Interop-Chat wie nachstehend beschrieben eine on-Demand-Besprechung erstellen:

- Wenn der Benutzer des Teams versucht, seinen Bildschirm freizugeben, wird automatisch eine Besprechung auf Anforderungs Teams erstellt, und ein Einladungslink zu dieser Besprechung wird an den Client des Skype for Business-Benutzers gesendet. Wenn Sie auf den Link klicken, wird der Skype for Business-Benutzer Teams öffnen und an der Besprechung teilnehmen. Beide Benutzer sind jetzt in einer Teams-Besprechung und können nach Bedarf freigeben.

- Wenn der Skype for Business-Benutzer einen Client von 2018 oder höher verwendet und versucht, Inhalte freizugeben, wird automatisch eine Skype for Business-on-Demand-Besprechung erstellt, und ein Einladungslink zu dieser Besprechung wird an den Client des Teams gesendet. Wenn Sie auf den Link klicken, versucht der Benutzer von Teams, an der Skype for Business-Besprechung teilzunehmen. Wenn der Benutzer des Teams den Skype for Business-Client installiert hat, wird er geöffnet, und der Benutzer wird aufgefordert, sich anzumelden (sofern er noch nicht angemeldet ist).  Wenn der Benutzer des Teams nicht über den Skype for Business-Client verfügt, wird der Benutzer aufgefordert, die Webversion zu verwenden. Nachdem beide Benutzer angemeldet sind, befinden Sie sich in einer Skype for Business-Besprechung und können Sie nach Bedarf freigeben.

## <a name="teams-conversations---interop-versus-native-threads"></a>Teams-Unterhaltungen – Interop versus native Threads

Da die Interop-Kommunikation nicht alle Features von Native Teams-Konversationen unterstützt, verwaltet der Team-Client getrennte Konversations Threads für Teams-zu-Teams und Teams-zu-Skype for Business-Kommunikation. Diese Unterhaltungen werden in der Benutzeroberfläche anders gerendert: Interop-Threads können von einem regulären systemeigenen Teams-Thread unterschieden werden:

- Fehlende Steuerungen für Rich-Text, Datei-und Bildschirmübertragung, Unfähigkeit zum Hinzufügen von Benutzern.
- Eine Änderung des Symbols des Zielbenutzers mit einem "s" für Skype for Business.

Diese Unterschiede werden in den folgenden Screenshots gezeigt:

Eine native Unterhaltung von Teams zu Teams mit dem Benutzer G3-Test

![Diagramm mit einer nativen Unterhaltung von Teams zu Teams](media/teams-upgrade-native-thread.png)

Eine Interop-Unterhaltung mit dem gleichen Benutzer G3-Test

![Diagramm mit einer Unterhaltung von Interop-Teams zu Teams](media/teams-upgrade-interop-thread.png)

Nachdem ein konversationsthread erstellt wurde, ändert sich dessen Typ nie. Nach der Erstellung wird ein Interop-Thread in Teams immer zum Skype for Business-Client des Zielbenutzers weitergeleitet. Ein systemeigener Thread wird immer an den Team-Client des Zielbenutzers weitergeleitet.  Wenn sich der Modus eines Empfänger Benutzers ändert, funktionieren vorhandene Teams für diesen Benutzer nicht mehr, und in diesem Chat wird eine Notiz mit einem Link angezeigt, um eine neue systemeigene Konversation zu starten, wie im folgenden Screenshot gezeigt.


![Diagramm, das einen Chat mit aktualisierten Skype for Business-Benutzern zeigt](media/teams-upgrade-chat-with-upgraded-sfb-user.png)

## <a name="presence"></a>Anwesenheit

Die Anwesenheitsinformationen für einen bestimmten Benutzer basieren auf der Aktivität des Benutzers im Dienst über den Client. Die Anwesenheitsinformationen werden dann für andere Benutzer veröffentlicht.  Skype for Business und Teams sind getrennte Dienste mit separaten Clients, sodass jeder Dienst seinen eigenen Anwesenheitsstatus für einen Benutzer hat.   Es gibt auch eine Synchronisierung zwischen den Anwesenheits Diensten in Teams und in Skype for Business Online.  Dadurch kann ein Dienst möglicherweise das vorhanden sein des Benutzers aus dem anderen Dienst veröffentlichen, falls erforderlich. 

Das Verhalten der Anwesenheits Veröffentlichung basiert auf dem Modus des Benutzers. Es gibt drei grundlegende Fälle:

- Wenn sich ein Benutzer im TeamsOnly-Modus befindet, sehen alle anderen Benutzer die Anwesenheit von Teams für diesen Benutzer, unabhängig davon, welchen Client Sie verwenden.

- Wenn sich ein Benutzer in einem der Skype for Business-Modi befindet, sehen alle anderen Benutzer die Skype for Business-Anwesenheit für diesen Benutzer, unabhängig davon, welchen Client Sie verwenden.

- Wenn sich ein Benutzer im Modus "Inseln" befindet, ist die in Skype for Business und Microsoft Teams veröffentlichte Anwesenheit unabhängig, sodass die Anwesenheitsanzeige für Benutzer innerhalb der gleichen Organisation vom Client des anderen Benutzers abhängt. Benutzer in Verbundorganisationen sehen die Anwesenheit dieses Benutzers auf der Grundlage Ihrer Skype for Business-Aktivität, da der Verbund Verkehr zu einem Nutzer der Inseln-Modus in Skype for Business landet.

Nehmen Sie beispielsweise an, dass Benutzer A sich im Modus "Inseln" befindet. Wenn Benutzer a in Microsoft Teams aktiv ist, aber nicht bei Skype for Business angemeldet ist, sehen andere Benutzer den Benutzer a als aktiv von Ihrem Team-Client, aber in Ihrem Skype for Business-Client sehen Benutzer a als offline. Dies ist beabsichtigt, da Benutzer A nicht erreicht werden kann, wenn Sie den Client nicht ausführen. 


## <a name="federation"></a>Partnerverbund

Föderation von Teams zu einem anderen Benutzer unter Verwendung von Skype for Business muss der Team Benutzer in Skype for Business online sein. TeamsUpgradePolicy steuert das Routing für eingehende Federated-Chats und-Anrufe. Das Verhalten des Verbund Routings ist identisch mit den Szenarien für denselben Mandanten, mit Ausnahme des Modus "Inseln". Wenn sich die Empfänger im Inseln-Modus befinden:

- Chats und Anrufe, die von Teams initiiert werden, landen in Skype for Business, wenn sich der Empfänger in einem Federated-Mandanten befindet.
- Chats und Anrufe, die von Teams initiiert werden, landen in Teams, wenn sich der Empfänger im gleichen Mandanten befindet.
- Chats und Anrufe, die von Skype for Business initiiert werden, landen immer in Skype for Business.

Ein Federated-Chat kann entweder ein systemeigener Thread oder ein Interop-Thread sein. Siehe [Teams-Unterhaltungen---Interop-versus-native-Threads](#teams-conversations---interop-versus-native-threads).

- Wenn sich der Empfänger und der Absender im TeamsOnly-Aktualisierungsmodus befinden, ist die Unterhaltung ein systemeigener Chat, in dem alle Rich-Messaging-und Anruffunktionen enthalten sind. Weitere Informationen finden Sie unter [systemeigene Chat-Erfahrung für externe (Verbund-) Benutzer in Teams](native-chat-for-external-users.md). 

- Befindet sich einer der Konversationsteilnehmer nicht im TeamsOnly-Upgrademodus, bleibt die Unterhaltung eine Interoperabilitäts Funktion mit nur-Text-Nachrichten. Die Benutzeroberfläche macht Federated-Chats auf ähnliche Weise für identische Mandanten-Interop-Threads verfügbar, es sei denn, es gibt eine Notiz, die angibt, dass der Benutzer extern ist.

Weitere Informationen finden Sie unter [Verwalten des externen Zugriffs in Microsoft Teams](manage-external-access.md) und der [systemeigenen Chatumgebung für externe (Verbund-) Benutzer in Teams](native-chat-for-external-users.md).

## <a name="contacts"></a>Kontakte

Teams und Skype for Business haben getrennte Kontaktlisten. Das bedeutet, dass die in einem System vorgenommenen Kontakt Ergänzungen,-Entfernungen und-Änderungen nicht mit dem anderen System synchronisiert werden. Kontakte von Skype for Business werden jedoch automatisch in Teams kopiert, wenn eines von zwei bestimmten Ereignissen Eintritt: 

- Bei einem Skype for Business Online-Benutzer werden die Kontakte aus Skype for Business bei der ersten Anmeldung in Teams in Teams kopiert.  Dieses Verhalten steht Benutzern mit einem lokalen Konto in Skype for Business Server nicht zur Verfügung.  

- Nachdem ein Benutzer auf TeamsOnly aktualisiert wurde (entweder über die Zuweisung von TeamsUpgradePolicy oder über Move-CsUser-MoveToTeams), wird das nächste Mal, wenn sich ein Benutzer bei Teams anmeldet, vorhandene Kontakte in Skype for Business mit vorhandenen Kontakten zusammengeführt, die bereits in Teams sind. Dieses Verhalten tritt auf, wenn das Skype for Business-Konto des Benutzers lokal oder online gehostet wird. 

In beiden Fällen ist die Übertragung von Kontakten von Skype for Business in Teams asynchron, daher kann es ein paar Minuten dauern, bis Kontakte in Teams angezeigt werden. Die beiden obigen Ereignisse lösen die Kopie aus.  

## <a name="related-links"></a>Verwandte Links

[Anleitungen zur Migration und Interoperabilität für Organisationen, die Teams zusammen mit Skype for Business verwenden](migration-interop-guidance-for-teams-with-skype.md) 

[Konfigurieren der Hybrid Konnektivität zwischen Skype for Business Server und Microsoft 365 oder Office 365](https://docs.microsoft.com/SkypeForBusiness/hybrid/configure-hybrid-connectivity)

[Verschieben von Benutzern zwischen lokalen Bereitstellungen und der Cloud](https://docs.microsoft.com/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud)

[Festlegen Ihrer Einstellungen für Koexistenz und Upgrades](setting-your-coexistence-and-upgrade-settings.md)

[Grant-CsTeamsUpgradePolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps)

[Verwenden des Besprechungs Migrations Diensts (MMS)](https://docs.microsoft.com/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)

