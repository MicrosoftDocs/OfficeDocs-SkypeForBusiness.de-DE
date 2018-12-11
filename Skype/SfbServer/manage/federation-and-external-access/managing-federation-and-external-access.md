---
title: 'Lync Server 2013: Verwalten von partnerverbünden und externen Zugriff auf Skype für Business Server'
ms:assetid: 26f806c1-f284-4637-b06b-06270336c540
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520966(v=OCS.15)
ms:contentKeyID: 48183665
mtps_version: v=OCS.15
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Aktivieren und Konfigurieren von Zugriff externer Benutzer auf das Steuerelement, ob mit internen Skype für Benutzer von Business Server unterstützte externe Benutzer zusammenarbeiten können.
ms.openlocfilehash: bc96f0d221071393b6c9ef7b7279159fdaa4468f
ms.sourcegitcommit: 5576463b0295e48e0506f7e4b44006ffc0b38a95
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2018
ms.locfileid: "27223122"
---
# <a name="managing-federation-and-external-access-to-skype-for-business-server"></a>Verwalten von partnerverbünden und externen Zugriff auf Skype für Business Server

Bereitstellen eines Edgeservers oder edgepool ist der erste Schritt zur Unterstützung von externer Benutzern. Weitere Informationen zum Bereitstellen von Edgeservern finden Sie unter [Edge-Server in Skype für Business Server bereitstellen](../../deploy/deploy-edge-server/deploy-edge-server.md).

Nach dem Installieren und Konfigurieren der internen bereitstellungs von Skype für Business Server, können interne Benutzer in Ihrer Organisation mit anderen internen Benutzern zusammenarbeiten, die SIP-Konten in Ihrer Active Directory-Domänendienste (AD DS) verfügen. Zusammenarbeit kann umfassen senden und Empfangen von Sofortnachrichten und Aktualisieren des Anwesenheitsstatus und die Teilnahme an Konferenzen (auch bekannt als "Besprechungen"). Aktivieren und Konfigurieren von Zugriff externer Benutzer auf das Steuerelement, ob mit internen Skype für Benutzer von Business Server unterstützte externe Benutzer zusammenarbeiten können. Externe Benutzer können Remotebenutzer Ihrer Bereitstellung, Verbundbenutzer (einschließlich unterstützten Benutzer des öffentlichen instant messaging (IM)-Dienstanbieter) und anonyme Teilnehmer in Konferenzen enthalten.

Wenn Ihre Bereitstellung die Installation von einer Skype für Business Server Edge-Server oder einem edgepool enthalten, wird der Bereich der möglichen Kommunikationstypen mit einer Anzahl von Optionen für den Zugriff durch externe Benutzer, die Kommunikation mit anderen SIP-Verbund Mitgliedern erheblich erweitert Domänen und SIP-partnerverbundanbieter. Nach dem Einrichten von den Edge-Server oder Edge-Pool, aktivieren die Typen von Zugriff durch externe Benutzer, die Sie bereitstellen möchten, und konfigurieren die Richtlinien zur Steuerung für den externen Zugriff. In Skype für Business Server aktivieren und Konfigurieren des Zugriffs externer Benutzer und Richtlinien, die mit der Skype Business Server-Systemsteuerung, der [Skype für Business Server-Verwaltungsshell](../management-shell.md)oder beide Grundlage der Anforderungen für die Aufgabe. 



> [!IMPORTANT]  
> Wenn Sie Ihre Konfiguration und die Richtlinien für den Zugriff externer Benutzer entwerfen, müssen Sie die Rangfolge von Richtlinien und Anwenden von Richtlinien für die verstehen. Skype für Business Server aufgeführt, die auf einer Richtlinienebene angewendet werden kann Einstellungen außer Kraft setzen, die auf einer anderen Richtlinienebene angewendet werden. Skype für Business Server RichtlinienPrioritäten ist: Benutzerrichtlinie (die meisten beeinflussen) überschreibt eine Standortrichtlinie, und klicken Sie dann eine Standortrichtlinie überschreibt eine globale Richtlinie (mindestens beeinflussen). Mit anderen Worten: Je geringer der Abstand zwischen Richtlinieneinstellung und betroffenem Objekt, desto stärker der Einfluss auf das Objekt.


Standardmäßig keine Richtlinien sind so konfiguriert, dass Sie Zugriff durch externe Benutzer, einschließlich des Zugriffs durch Remotebenutzer unterstützen, Benutzerzugriff, Verbund, auch wenn Sie bereits Access-Unterstützung externer Benutzer für Ihre Organisation aktiviert haben. Um die Verwendung der Zugriff durch externe Benutzer zu kontrollieren, müssen Sie eine oder mehrere Richtlinien, konfigurieren und dabei die Art der Zugriff durch externe Benutzer für jede Richtlinie unterstützt. Dazu gehören die folgenden Richtlinien für externen Zugriff:

  - **Globale Richtlinie**   die globale Richtlinie wird erstellt, wenn Sie Edgeserver bereitstellen. Standardmäßig sind keine Access-Optionen für externe Benutzer in der globalen Richtlinie aktiviert. Zur Unterstützung der Zugriff durch externe Benutzer auf globaler Ebene konfigurieren Sie die globale Richtlinie, um eine oder mehrere Arten von Zugriffsoptionen für externe Benutzer unterstützen. Die globale Richtlinie gilt für alle Benutzer in Ihrer Organisation, jedoch Standortrichtlinien und Benutzerrichtlinien überschreiben die globale Richtlinie. Wenn Sie die globale Richtlinie löschen, Sie ihn nicht entfernen. Stattdessen müssen Sie Sie sie auf die Standardeinstellung.

  - **Site-Richtlinie**   Sie erstellen und konfigurieren Sie eine können oder weitere Richtlinien zur Begrenzung für externe Benutzerzugriff auf bestimmte Websites unterstützen. Die Konfiguration in der Standortrichtlinie setzt die globale Richtlinie außer Kraft, jedoch nur für den durch die Standortrichtlinie abgedeckten Standort. Wenn Sie in der globalen Richtlinie Zugriff durch Remotebenutzer aktivieren, können Sie beispielsweise eine Standortrichtlinie angeben, die Zugriff durch Remotebenutzer für einen bestimmten Standort deaktiviert. Standardmäßig wird eine Standortrichtlinie auf alle Benutzer dieser Website angewendet, jedoch können Sie eine Benutzerrichtlinie für einen Benutzer die Website-Einstellung außer Kraft gesetzt zuweisen.

  - **Benutzerrichtlinie**   können Sie erstellen und konfigurieren Sie eine oder mehrere Richtlinien für Benutzer beschränken für Remotebenutzerzugriff auf bestimmte Benutzer unterstützen. Die Konfiguration in der Benutzer außer Kraft setzt die globale und Richtlinien für den Standort, jedoch nur für bestimmte Benutzer, die die Richtlinie zugewiesen ist. Wenn Sie in der globalen Richtlinie und Standortrichtlinie Zugriff durch Remotebenutzer aktivieren, können Sie beispielsweise geben eine Benutzerrichtlinie, die Zugriff durch Remotebenutzer deaktiviert und weisen Sie diese Richtlinie auf bestimmte Benutzer. Wenn Sie eine Benutzerrichtlinie erstellen, müssen Sie es an einen oder mehrere Benutzer anwenden, bevor sie wirksam wird.

Um zu bestimmen, welche Konfigurationseinstellungen und Richtlinien müssen Sie erstellen oder bearbeiten, finden Sie in der folgenden Entscheidungspunkte:

**Möchten Sie interne und externe Benutzer Ihre Domäne auf Zusammenarbeit per Sofortnachrichten, Webkonferenzen und Audio/Video werden können?**

Konfigurieren Sie die Einstellungen, wie in den Themen [Configure Policies Remotebenutzer hinsichtlich steuern](external-access-policies/configure-policies-to-control-remote-user-access.md), und [Aktivieren oder Deaktivieren des partnerverbunds und öffentlichen Instant Messaging-Diensten](access-edge/enable-or-disable-federation-and-public-im-connectivity.md).

**Möchten Sie zulassen, dass anonyme Benutzer teilnehmen und Konferenzen, die von Benutzern in Ihrer Bereitstellung eingeladen werden?**

Konfigurieren Sie die Einstellungen, wie im Thema [Zuweisen von konferenzrichtlinien zur Unterstützung anonymer Benutzer](access-edge/assign-conferencing-policies-to-support-anonymous-users.md) und [konferenzrichtlinien erstellen](../conferencing/create-policies.md).

**Möchten Sie Benutzern die Kommunikation mit SIP-Partnerverbunddomänen-Kontakten erlauben?**

Konfigurieren Sie die Einstellungen, wie in den Themen [Configure Richtlinien zur Steuerung des Benutzerzugriffs federated](external-access-policies/configure-policies-to-control-federated-user-access.md), [Aktivieren oder Deaktivieren des partnerverbunds und öffentlichen Instant Messaging-Diensten](access-edge/enable-or-disable-federation-and-public-im-connectivity.md)und [Verwalten von SIP-verbunddomänen für Ihre Organisation](sip-domains/manage-sip-federated-domains-for-your-organization.md).


**Wenn Sie die Kommunikation mit SIP-Partververbunddomänen aktiviert haben, möchten Sie die automatische Ermittlung der SIP-Partnerverbund aktivieren?**

Konfigurieren Sie die Einstellungen, wie im Thema [Aktivieren oder Deaktivieren der Ermittlung von Verbundpartnern](access-edge/enable-or-disable-discovery-of-federation-partners.md).

**Wenn Sie die Kommunikation mit SIP-Partververbunddomänen aktiviert haben, möchten Sie damit das Senden eines Haftungsausschluss Federated Kontakten benachrichtigen, dass Sie die Archivierung verwenden und Kommunikation archiviert werden können?**

Konfigurieren Sie die Einstellungen, wie im Thema [Aktivieren oder deaktivieren Sie das Senden einer Archiving Disclaimer an Verbundpartner in](access-edge/enable-or-disable-sending-an-archiving-disclaimer-to-federated-partners.md).

**Möchten Sie zulassen, dass Benutzer die Kommunikation mit SIP Federated Providers die Kommunikation mit öffentlichen Anbieter unterstützt werden?**

Konfigurieren die Einstellungen wie in den Themen [Configure Richtlinien zur Steuerung öffentliche Benutzer zugreifen](external-access-policies/configure-policies-to-control-public-user-access.md), [Aktivieren oder Deaktivieren des partnerverbunds und öffentlichen Instant Messaging-Diensten](access-edge/enable-or-disable-federation-and-public-im-connectivity.md)und [Erstellen oder Bearbeiten von öffentlichen SIP-verbundanbietern](sip-providers/manage-sip-federated-providers-for-your-organization.md#create-or-edit-public-sip-federated-providers-in-skype-for-business-server) beschrieben


**Möchten Sie zulassen, dass Benutzer die Kommunikation mit SIP Federated Providers, die unter Microsoft Office 365 und Skype für Business Online gehostete Anbieter sind?**

Konfigurieren Sie die Einstellungen, wie in den Themen [Aktivieren oder Deaktivieren des partnerverbunds und öffentlichen Instant Messaging-Diensten](access-edge/enable-or-disable-federation-and-public-im-connectivity.md) und [Erstellen oder Bearbeiten von gehosteten SIP-verbundanbietern](sip-providers/manage-sip-federated-providers-for-your-organization.md#create-or-edit-hosted-sip-federated-providers-in-skype-for-business-server).

**Wird in der Bereitstellung konfiguriert in einer Domäne Split (auch bekannt als Hybrid), wobei einige Benutzer haben ihre Homeserver in einer lokalen Bereitstellung und andere Benutzer mit einem Homeserver in online-Umgebung konfiguriert werden?**

Konfigurieren die Einstellungen wie in den Themen [Configure Richtlinien zur Steuerung des Zugriffs für Verbundbenutzer](external-access-policies/configure-policies-to-control-federated-user-access.md) [Aktivieren oder Deaktivieren des partnerverbunds und öffentlichen Instant Messaging-Diensten](access-edge/enable-or-disable-federation-and-public-im-connectivity.md)und [Erstellen oder Bearbeiten von gehosteten SIP-verbundanbietern](sip-providers/manage-sip-federated-providers-for-your-organization.md#create-or-edit-hosted-sip-federated-providers-in-skype-for-business-server)beschrieben.


Sie können externe Benutzer Zugriff auf Einstellungen für alle Richtlinien, die Sie verwenden zum Steuern des Zugriffs externer Benutzer, selbst wenn Sie nicht den Zugriff externer Benutzer für Ihre Organisation aktiviert haben möchten sowie konfigurieren. Werden jedoch die Richtlinien und anderen Einstellungen, die Sie konfigurieren nur wirksam, wenn Zugriff durch externe Benutzer für Ihre Organisation aktiviert haben. Externe Benutzer können nicht mit Benutzern in Ihrer Organisation kommunizieren, wenn Zugriff durch externe Benutzer deaktiviert ist, oder wenn keine Richtlinien für den externen Benutzerzugriff für die Unterstützung konfiguriert werden.

Ihre edgebereitstellung authentifiziert die Typen von externen Benutzern (außer für anonyme Benutzer, die Konferenz-ID und ein Kennwort, das die anonymen Teilnehmer gesendet wird, wenn Sie der Konferenz und einladen Teilnehmer erstellen authentifiziert werden) und Steuerelemente Zugriff auf Grundlage der Konfiguration Ihrer edgeunterstützung. Um die Kommunikation zu steuern, können Sie eine oder mehrere Richtlinien konfigurieren und Konfigurieren von Einstellungen, die definieren, wie Benutzer innerhalb und außerhalb Ihrer Bereitstellung miteinander kommunizieren. Die Richtlinien und Einstellungen gehören die globale Richtlinie für den Zugriff durch externe Benutzer neben Standort- und Benutzerrichtlinien, die Sie erstellen und konfigurieren, um eine oder mehrere Arten von Zugriff durch externe Benutzer für bestimmte Standorte oder Benutzer aktivieren können.

