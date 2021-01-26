---
title: Liste der Tabellen für den Server für beständigen Chat
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 10/20/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 26c9e271-3516-4d90-b930-70fec4e359ea
description: Das Datenbankschema für beständigen Chat besteht aus den folgenden Tabellen.
ms.openlocfilehash: fc87faee92856f35c1ebd54dae4db1f01cfe646b
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49813015"
---
# <a name="list-of-persistent-chat-server-tables"></a>Liste der Tabellen für den Server für beständigen Chat
 
Das Datenbankschema für beständigen Chat besteht aus den folgenden Tabellen.
  
## <a name="active-directory-sync"></a>Active Directory-Synchronisierung

|**Table**|**Beschreibung**|
|:-----|:-----|
|[tblADCookie](tbladcookie.md) <br/> |Enthält die aktuellen LDAP-Synchronisierungscookies (Lightweight Directory Access-Protokoll). Jede Zeile entspricht einer Active Directory Domain Services-Domäne, die der Server für beständigen Chat aktiv auf Änderungen überwacht. (In dieser Tabelle werden nur die Active Directory-Domänen dargestellt, die für den Server für beständigen Chat relevant sind.)  <br/> |
|[tblPrincipalMemberDifference](tblprincipalmemberdifference.md) <br/> |Enthält Gruppenmitgliedschaftsänderungen (hinzugefügte und entfernte Mitglieder), die noch nicht von den späteren Active Directory-Synchronisierungsschritten verarbeitet wurden und eine der temporären Tabellen (zusammen mit der Tabelle "tblADUpdates") sind, die im ersten Schritt der Active Directory-Synchronisierung verwendet werden.  <br/> Mitgliedschaftsänderungen werden nur für Gruppen gespeichert und/oder verarbeitet, die in der  tblPrincipal-Tabelle aufgelistet sind oder für die hier bereits Mitglieder aufgelistet sind.  <br/> |
|[tblADUpdates](tbladupdates.md) <br/> |Enthält Änderungen an Active Directory-Domänendiensten, die noch nicht von den späteren Active Directory-Synchronisierungsschritten verarbeitet wurden, und ist eine der temporären Tabellen (zusammen mit der Tabelle "tblPrincipalMemberDifference"), die im ersten Schritt der Active Directory-Synchronisierung verwendet wird.  <br/> Änderungen an Active Directory werden nur für Prinzipale gespeichert, verarbeitet oder beides nur für Prinzipale, die bereits in der Tabelle "tblPrincipal" aufgeführt sind.  <br/> |
|[tblPrincipalMembers](tblprincipalmembers.md) <br/> |Enthält Prinzipalmitgliedschaften.  <br/> |
|[tblPrincipalMeta](tblprincipalmeta.md) <br/> |Enthält die Prinzipale, die aus Active Directory aktualisiert werden müssen.  <br/> |
|[tblSkippedAffiliations](tblskippedaffiliations.md) <br/> |Enthält Zuordnungen, die aus einem bestimmten Grund, in der Regel aufgrund von Active Directory-Zugriffsfehlern, nicht aktualisiert werden konnten.  <br/> Diese Tabelle dient nur zu Informationszwecken. Der Inhalt dieser Tabelle wird nicht verwendet.  <br/> Die Prinzipale mit Zugehörigkeiten, die nicht ordnungsgemäß aktualisiert werden konnten, werden in der tblPrincipalMeta-Tabelle gespeichert und bei Gelegenheit aktualisiert.  <br/> |
   
## <a name="principals-affiliations-nodes-scopes-and-roles"></a>Prinzipale, Zugehörigkeiten, Knoten, Bereiche und Rollen

|**Table**|**Beschreibung**|
|:-----|:-----|
|[tblPrincipalType](tblprincipaltype.md) <br/> |Enthält Prinzipaltypen zur Kategorisierung des Inhalts der Tabelle tblPrincipal. Diese Tabelle ist statisch. Sie wird beim Erstellen der Datenbank eingerichtet und nicht geändert.  <br/> |
|[tblPrincipal](tblprincipal.md) <br/> |Enthält alle Prinzipale (Benutzer, Ordner, Gruppen usw.). Der Server für beständigen Chat behandelt dies als flache heterogene Liste. Verschiedene Spalten basieren auf dem Typ des jeweiligen Prinzipals.  <br/> Die meisten dieser Prinzipale sind zwischengespeicherte Kopien von Objekten, die in Active Directory gespeichert sind. Das Erstellen der zwischengespeicherten Kopie in der Prinzipaltabelle dieser Active Directory-Objekte wird als Bereitstellung bezeichnet.  <br/> Einige Prinzipale werden aggressiver erstellt als andere, und einige Active Directory-Objekte werden vollständig ignoriert.  <br/> |
|[tblPrincipalAffiliations](tblprincipalaffiliations.md) <br/> |Enthält Prinzipalmitgliedschaften, die Mitgliedschaften in Active Directory-Sicherheitsgruppen, Active Directory-Containern und so weiter beschreiben.  <br/> |
|[tblNode](tblnode.md) <br/> |Enthält den Kategorieknoten, wie in der Systemsteuerung verwaltet.  <br/> |
|[tblRoleType](tblroletype.md) <br/> |Enthält Rollentypen und die zugehörigen Berechtigungsgruppen. Diese Nachschlagetabelle ist statisch.  <br/> |
|[tblScopePrincipal](tblscopeprincipal.md) <br/> |Enthält Bereiche, die Knoten zugewiesen sind.  <br/> |
|[tblPrincipalRole](tblprincipalrole.md) <br/> |Enthält Rollen, die Knoten zugewiesen sind.  <br/> |
|[tblSiopWhiteList](tblsiopwhitelist.md) <br/> |Enthält die registrierten Add-Ins, die Knoten zugeordnet werden können.  <br/> |
|[tblEnumAttribute](tblenumattribute.md) <br/> |Enthält nur die hartcodierten Attribute Visibility und Behavior, die in der tblNode-Tabelle verwendet werden.  <br/> |
|[tblEnumValue](tblenumvalue.md) <br/> |Enthält die Werte der hartcodierten Attribute "Visibility" und "Behavior", die in der Tabelle "tblNode" verwendet werden.  <br/> |
   
## <a name="invites-chats-and-other-client-support"></a>Einladungen, Chats und sonstige Clientunterstützung

|**Table**|**Beschreibung**|
|:-----|:-----|
|[tblPrincipalInvites](tblprincipalinvites.md) <br/> |Enthält Einladungen für alle bereitgestellten Benutzer im System für alle Knoten mit aktivierter automatischer Einladung.  <br/> |
|[tblChat](tblchat.md) <br/> |Enthält alle Chatnachrichten.  <br/> |
|[tblLastInviteId](tbllastinviteid.md) <br/> |Enthält die letzte Einladungs-ID, die für jeden Benutzer generiert (und in der tblPrincipalInvite-Tabelle) verwendet wurde.  <br/> |
|[tblLastChatId](tbllastchatid.md) <br/> |Enthält die letzte Chat-ID, die für jeden Benutzer generiert (und in der tblChat-Tabelle) verwendet wurde.  <br/> |
|[tblPreference](tblpreference.md) <br/> |Enthält Benutzerclienteinstellungen (nur von Legacyclients verwendet).  <br/> |
|[tblFileToken](tblfiletoken.md) <br/> |Enthält temporäre Token für Dateiübertragungszwecke. Jedes Mal, wenn eine Datei hochgeladen oder heruntergeladen wird, generiert der Dienst für beständigen Chat ein Token, das der Client für den Zugriff auf den Dateispeicher des Webdiensts verwendet.  <br/> |
   
## <a name="server-support"></a>Serverunterstützung

|**Table**|**Beschreibung**|
|:-----|:-----|
|[tblServerIdentity](tblserveridentity.md) <br/> |Enthält die aktiven Server im Pool für den Server für beständigen Chat.  <br/> |
|[tblAdminLock](tbladminlock.md) <br/> |Enthält die Administratorsperre für die Ausführung einiger Administratorbefehle. Der Systemrevisionseintrag in der tblSystemRevision -Tabelle wird nach jeder Freigabe der Sperre schrittweise erhöht.  <br/> |
|[tblSystemRevision](tblsystemrevision.md) <br/> |Enthält den Revisionsnummerneintrag, der (zusammen mit der AdminLock-Tabelle) zur Einhaltung der Konsistenz bei mehreren Servern verwendet wird.  <br/> |
|[tblActivePeers](tblactivepeers.md) <br/> |Enthält aktuelle Peer-zu-Peer-Verbindungen zwischen Diensten für beständigen Chat.  <br/> |
|[tblConfig](tblconfig.md) <br/> |Enthält die nicht unterstützte Konfiguration des Servers für beständigen Chat.  <br/> |
   

