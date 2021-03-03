---
title: 'Lync Server 2013: Verwalten des Verbunds und des externen Zugriffs auf Skype for Business Server'
ms.reviewer: ''
ms:assetid: 26f806c1-f284-4637-b06b-06270336c540
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520966(v=OCS.15)
ms:contentKeyID: 48183665
mtps_version: v=OCS.15
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Sie aktivieren und konfigurieren den Externen Benutzerzugriff, um zu steuern, ob unterstützte externe Benutzer mit internen Skype for Business Server-Benutzern zusammenarbeiten können.
ms.openlocfilehash: df8ca25dcaffb9ee563691eb327dc9ea6e9a229c
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49826605"
---
# <a name="managing-federation-and-external-access-to-skype-for-business-server"></a>Verwalten des Verbunds und des externen Zugriffs auf Skype for Business Server

Die Bereitstellung eines Edgeservers oder Edgepools ist der erste Schritt zur Unterstützung externer Benutzer. Weitere Informationen zum Bereitstellen von Edgeservern finden Sie unter ["Bereitstellen von Edgeservern in Skype for Business Server".](../../deploy/deploy-edge-server/deploy-edge-server.md)

Nach der Installation und Konfiguration Ihrer internen Bereitstellung von Skype for Business Server können interne Benutzer in Ihrer Organisation mit anderen internen Benutzern zusammenarbeiten, die über EIN -SIP-Konto in Ihren Active Directory Domain Services (AD DS) verfügen. Die Zusammenarbeit kann das Senden und Empfangen von Chatnachrichten, die Aktualisierung des Anwesenheitsstatus und die Teilnahme an Konferenzen (auch als "Besprechungen" bezeichnet) umfassen. Sie aktivieren und konfigurieren den Externen Benutzerzugriff, um zu steuern, ob unterstützte externe Benutzer mit internen Skype for Business Server-Benutzern zusammenarbeiten können. Externe Benutzer können Remotebenutzer Ihrer Bereitstellung, Verbundbenutzer (einschließlich unterstützter Benutzer von Dienstanbietern für öffentliche Chatnachrichten) und anonyme Teilnehmer an Konferenzen umfassen.

Wenn Ihre Bereitstellung die Installation eines Skype for Business Server-Edgeservers oder eines Edgepools umfasst, wird der Bereich möglicher Kommunikationstypen um eine Reihe von Optionen für den Externen Benutzerzugriff, die Kommunikation mit Mitgliedern anderer SIP-Verbunddomänen und sip-Verbundanbieter erheblich erweitert. Nach dem Einrichten des Edgeservers oder Edgepools aktivieren Sie die Typen des externen Benutzerzugriffs, den Sie bereitstellen möchten, und konfigurieren die Richtlinien für die Steuerung des externen Zugriffs. In Skype for Business Server aktivieren und konfigurieren Sie den Externen Benutzerzugriff und Richtlinien basierend auf den Aufgabenanforderungen über die Skype for Business Server-Systemsteuerung, die [Skype for Business Server-Verwaltungsshell](../management-shell.md)oder beides. 



> [!IMPORTANT]  
> Beim Entwerfen der Konfiguration und der Richtlinien für externen Benutzerzugriff müssen Sie die Rangfolge der Richtlinien verstehen und wissen, wie Richtlinien angewendet werden. Skype for Business Server-Richtlinieneinstellungen, die auf einer Richtlinienebene angewendet werden, können Einstellungen außer Kraft setzen, die auf einer anderen Richtlinienebene angewendet werden. Prioritätenreihenfolge für Skype for Business Server-Richtlinien: Eine Benutzerrichtlinie (größter Einfluss) hat Vorrang vor einer Standortrichtlinie, und eine Standortrichtlinie wiederum hat Vorrang vor einer globalen Richtlinie (geringster Einfluss). Dies bedeutet Folgendes: Je näher sich die Richtlinieneinstellung am betroffenen Objekt befindet, umso mehr Einfluss auf das Objekt hat sie.


Standardmäßig werden keine Richtlinien zur Unterstützung des Zugriffs durch externe Benutzer konfiguriert, einschließlich des Zugriffs durch Remotebenutzer und durch Partnerbenutzer, auch dann nicht, wenn Sie die Unterstützung für den Zugriff durch externe Benutzer bereits für Ihre Organisation aktiviert haben. Zur Steuerung des Zugriffs durch externe Benutzer müssen Sie eine oder mehrere Richtlinien konfigurieren und den für jede Richtlinie unterstützten Typ des externen Benutzerzugriffs angeben. Hierzu gehören die folgenden Richtlinien für den externen Zugriff:

  - **Globale Richtlinie**   Die globale Richtlinie wird erstellt, wenn Sie Ihre Edgeserver bereitstellen. Standardmäßig sind in der globalen Richtlinie keine Optionen für den externen Benutzerzugriff aktiviert. Zur Unterstützung des Zugriffs durch externe Benutzer auf globaler Ebene konfigurieren Sie die globale Richtlinie so, dass mindestens ein Typ des externen Benutzerzugriffs unterstützt wird. Die globale Richtlinie gilt für alle Benutzer in Ihrer Organisation, wird jedoch durch Standort- und Benutzerrichtlinien außer Kraft gesetzt. Wenn Sie die globale Richtlinie löschen, wird diese nicht entfernt. Stattdessen wird sie auf die Standardeinstellung zurückgesetzt.

  - **Standortrichtlinie**   Sie können eine oder mehrere Websiterichtlinien erstellen und konfigurieren, um die Unterstützung für den externen Benutzerzugriff auf bestimmte Websites zu beschränken. Die Konfiguration in der Standortrichtlinie setzt die globale Richtlinie außer Kraft, jedoch nur für den durch die Standortrichtlinie abgedeckten Standort. Wenn Sie beispielsweise den Remotebenutzerzugriff in der globalen Richtlinie aktivieren, können Sie eine Standortrichtlinie festlegen, die den Remotebenutzerzugriff für einen bestimmten Standort deaktiviert. Standardmäßig wird eine Standortrichtlinie auf alle Benutzer des jeweiligen Standorts angewendet, Sie können jedoch einem Benutzer eine Benutzerrichtlinie zuweisen, um die Standortrichtlinieneinstellung außer Kraft zu setzen.

  - **Benutzerrichtlinie**   Sie können eine oder mehrere Benutzerrichtlinien erstellen und konfigurieren, um die Unterstützung für den Remotebenutzerzugriff auf bestimmte Benutzer zu beschränken. Dies gilt jedoch nur für die von der entsprechenden Richtlinie betroffenen Benutzer. Wenn Sie beispielsweise den Remotebenutzerzugriff in der globalen Richtlinie und in der Standardrichtlinie aktivieren, können Sie eine Benutzerrichtlinie festlegen, die den Remotebenutzerzugriff deaktiviert, und diese Richtlinie bestimmten Benutzern zuweisen. Benutzerrichtlinien werden erst mit der Zuweisung zu bestimmten Benutzern wirksam.

Anhand der folgenden Entscheidungspunkte können Sie ermitteln, welche Konfigurationseinstellungen und Richtlinien Sie erstellen oder bearbeiten müssen:

**Möchten Sie internen und externen Benutzern Ihrer Domänen die Zusammenarbeit per Chat, Webkonferenzen und Audio/Video erlauben?**

Konfigurieren Sie die Einstellungen, [](external-access-policies/configure-policies-to-control-remote-user-access.md)wie in den Themen "Konfigurieren von Richtlinien zum Steuern der Zugriffe von Remotebenutzern" und "Aktivieren oder Deaktivieren von Verbund- und Verbindungen mit öffentlichen [Verbindungen mit öffentlichen Benutzern".](access-edge/enable-or-disable-federation-and-public-im-connectivity.md)

**Möchten Sie zulassen, dass anonyme Benutzer an Konferenzen teilnehmen können, die von Benutzern in Ihrer Bereitstellung gehostet werden?**

Konfigurieren Sie die Einstellungen, [](access-edge/assign-conferencing-policies-to-support-anonymous-users.md) wie im Thema "Zuweisen von Konferenzrichtlinien zur Unterstützung anonymer Benutzer" und "Erstellen von [Konferenzrichtlinien" beschrieben.](../conferencing/create-policies.md)

**Möchten Sie Benutzern die Kommunikation mit SIP-Partnerverbunddomänen-Kontakten erlauben?**

Konfigurieren Sie die Einstellungen, [](external-access-policies/configure-policies-to-control-federated-user-access.md)wie in den Themen "Konfigurieren von Richtlinien zum Steuern des Partnerbenutzerzugriffs", "Aktivieren oder Deaktivieren von Partnerverbund- und Verbindungen mit öffentlichen [Verbindungen"](access-edge/enable-or-disable-federation-and-public-im-connectivity.md)und "Verwalten von SIP-Verbunddomänen für [Ihre Organisation" ausführlich.](sip-domains/manage-sip-federated-domains-for-your-organization.md)


**Wenn Sie die Kommunikation mit SIP-Verbunddomänen aktiviert haben, möchten Sie die automatische Ermittlung des SIP-Verbunds aktivieren?**

Konfigurieren Sie die Einstellungen, wie im Thema "Aktivieren oder [Deaktivieren der Suche von Verbundpartnern" beschrieben.](access-edge/enable-or-disable-discovery-of-federation-partners.md)

**Wenn Sie die Kommunikation mit SIP-Partververbunddomänen aktiviert haben, möchten Sie das Senden eines Haftungsausschlusses an die Partnerverbundkontakte aktivieren, um sie über eine mögliche Archivierung der Kommunikation zu informieren?**

Konfigurieren Sie die Einstellungen wie im Thema "Aktivieren oder Deaktivieren des Sendens eines Archivierungsausschlusses an [Verbundpartner in" beschrieben.](access-edge/enable-or-disable-sending-an-archiving-disclaimer-to-federated-partners.md)

**Möchten Sie Benutzern die Kommunikation mit SIP-Verbundanbietern ermöglichen, die die Kommunikation mit öffentlichen Anbietern ermöglichen?**

Konfigurieren Sie die Einstellungen, [](external-access-policies/configure-policies-to-control-public-user-access.md)wie in den Themen "Konfigurieren von Richtlinien zum Steuern des Zugriffs durch öffentliche Benutzer", ["Aktivieren](access-edge/enable-or-disable-federation-and-public-im-connectivity.md)oder Deaktivieren von Partnerverbunden und Verbindungen mit öffentlichen Verbindungen mit öffentlichen Verbindungen" und "Erstellen oder Bearbeiten öffentlicher [SIP-Verbundanbieter" ausführlich.](sip-providers/manage-sip-federated-providers-for-your-organization.md#create-or-edit-public-sip-federated-providers-in-skype-for-business-server)


**Möchten Sie Benutzern die Kommunikation mit SIP-Verbundanbietern ermöglichen, bei denen es sich um gehostete Anbieter mit Microsoft 365 oder Office 365 und Skype for Business Online handelt?**

Konfigurieren Sie die Einstellungen, [](access-edge/enable-or-disable-federation-and-public-im-connectivity.md) wie in den Themen "Partnerverbund und Verbindung mit öffentlichen Verbindungen aktivieren oder deaktivieren" und Erstellen oder Bearbeiten von gehosteten [SIP-Verbundanbietern.](sip-providers/manage-sip-federated-providers-for-your-organization.md#create-or-edit-hosted-sip-federated-providers-in-skype-for-business-server)

**Ist Ihre Domäne als geteilte Domäne (auch als Hybridomäne bezeichnet) konfiguriert, in der einige Benutzer einen Homeserver in einer lokalen Bereitstellung haben und für andere Benutzer ein Homeserver in einer Onlineumgebung konfiguriert ist?**

Konfigurieren Sie die Einstellungen, [](external-access-policies/configure-policies-to-control-federated-user-access.md)wie in den Themen "Konfigurieren von Richtlinien zum Steuern des Partnerbenutzerzugriffs", "Aktivieren oder Deaktivieren von Verbund- und Verbindungen mit öffentlichen [Verbindungen"](access-edge/enable-or-disable-federation-and-public-im-connectivity.md)und "Erstellen oder Bearbeiten von gehosteten [SIP-Verbundanbietern".](sip-providers/manage-sip-federated-providers-for-your-organization.md#create-or-edit-hosted-sip-federated-providers-in-skype-for-business-server)


Sie können auch dann Einstellungen für den Zugriff externer Benutzer konfigurieren, wenn Sie den externen Benutzerzugriff für Ihre Organisation nicht aktiviert haben. Hierzu gehören auch Richtlinien, die Sie zum Steuern des externen Benutzerzugriffs verwenden möchten. Die von Ihnen konfigurierten Richtlinien und anderen Einstellungen treten jedoch erst in Kraft, wenn der externe Benutzerzugriff für Ihre Organisation aktiviert wird. Externe Benutzer können nicht mit Benutzern Ihrer Organisation kommunizieren, wenn der externe Benutzerzugriff deaktiviert ist oder wenn keine Richtlinien für den externen Benutzerzugriff konfiguriert wurden.

Ihre Edgebereitstellung authentifiziert die Typen externer Benutzer (außer Benutzer, die mit der Konferenz-ID und dem an den anonymen Teilnehmer übermittelten Hauptschlüssel identifiziert werden, wenn Sie die Konferenz erstellen und Teilnehmer einladen) und steuert den Zugriff basierend auf der Konfiguration der Edgeunterstützung. Zum Steuern der Kommunikation können Sie eine oder mehrere Richtlinien sowie Einstellungen konfigurieren, durch die definiert wird, wie Benutzer innerhalb und außerhalb der Bereitstellung miteinander kommunizieren. Zu den Richtlinien und Einstellungen gehören die globale Standardrichtlinie für den externen Benutzerzugriff sowie Richtlinien auf Standort- und Benutzerebene, die Sie zum Aktivieren eines oder mehrerer Typen des externen Benutzerzugriffs für bestimmte Standorte oder Benutzer erstellen und konfigurieren können.

