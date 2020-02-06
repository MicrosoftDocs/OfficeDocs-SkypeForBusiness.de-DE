---
title: Liste der Tabellen für den Server für beständigen Chat
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 10/20/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 26c9e271-3516-4d90-b930-70fec4e359ea
description: Das Datenbank-Schema des beständigen Chats besteht aus den folgenden Tabellen.
ms.openlocfilehash: ae6e1a260cb167397da83d79d37b92067d2ae99d
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41814753"
---
# <a name="list-of-persistent-chat-server-tables"></a>Liste der Tabellen für den Server für beständigen Chat
 
Das Datenbank-Schema des beständigen Chats besteht aus den folgenden Tabellen.
  
## <a name="active-directory-sync"></a>Active Directory-Synchronisierung

|**Tabelle**|**Beschreibung**|
|:-----|:-----|
|[tblADCookie](tbladcookie.md) <br/> |Enthält die aktuellen LDAP-Synchronisierungs Cookies (Lightweight Directory Access Protocol). Jede Zeile entspricht einer Active Directory-Domänendienst Domäne, die vom beständigen Chat Server aktiv auf Änderungen überwacht wird. (In dieser Tabelle werden nur die Active Directory-Domänen dargestellt, die für den beständigen Chat Server relevant sind.)  <br/> |
|[tblPrincipalMemberDifference](tblprincipalmemberdifference.md) <br/> |Enthält Änderungen an Gruppenmitgliedschaften (sowohl hinzugefügte als auch entfernte Mitglieder), die noch nicht von den späteren Active Directory-Synchronisierungs Schritten verarbeitet wurden und eine der temporären Tabellen (zusammen mit der tblADUpdates-Tabelle) sind, die im ersten Schritt der Active Directory-Synchronisierung verwendet werden.  <br/> Mitgliedschaftsänderungen werden gespeichert, verarbeitet oder beides, nur für Gruppen, die in der tblPrincipal-Tabelle aufgelistet sind oder in denen bereits Mitglieder aufgelistet sind.  <br/> |
|[tblADUpdates](tbladupdates.md) <br/> |Enthält Änderungen an Active Directory-Domänendiensten, die noch nicht von den späteren Active Directory-Synchronisierungs Schritten verarbeitet wurden und eine der temporären Tabellen (zusammen mit der tblPrincipalMemberDifference-Tabelle) sind, die im ersten Schritt von Active Directory verwendet werden. Synchronisieren.  <br/> Änderungen an Active Directory werden nur für Prinzipale gespeichert, verarbeitet oder beides, die bereits in der tblPrincipal-Tabelle aufgeführt sind.  <br/> |
|[tblPrincipalMembers](tblprincipalmembers.md) <br/> |Enthält Prinzipal Mitgliedschaften.  <br/> |
|[tblPrincipalMeta](tblprincipalmeta.md) <br/> |Enthält die Prinzipale, die aus Active Directory aktualisiert werden müssen.  <br/> |
|[tblSkippedAffiliations](tblskippedaffiliations.md) <br/> |Enthält Zugehörigkeiten, die aus irgendeinem Grund nicht aktualisiert werden konnten, in der Regel aufgrund von Active Directory-Zugriffsfehlern.  <br/> Diese Tabelle dient nur zu Informationszwecken. Der Inhalt wird nicht verwendet.  <br/> Die Prinzipale mit Zuordnungen, die nicht ordnungsgemäß aktualisiert werden konnten, werden in der tblPrincipalMeta-Tabelle aufbewahrt und erhalten eine weitere Chance, aktualisiert zu werden.  <br/> |
   
## <a name="principals-affiliations-nodes-scopes-and-roles"></a>Prinzipale, Zuordnungen, Knoten, Bereiche und Rollen

|**Tabelle**|**Beschreibung**|
|:-----|:-----|
|[tblPrincipalType](tblprincipaltype.md) <br/> |Enthält Prinzipaltypen, um zu kategorisieren, was in der tblPrincipal-Tabelle enthalten ist. Diese Tabelle ist statisch. Sie wird während der Datenbankerstellung eingerichtet und ändert sich nicht.  <br/> |
|[tblPrincipal](tblprincipal.md) <br/> |Enthält alle Prinzipale (Benutzer, Ordner, Gruppen usw.). Der Server für beständigen Chat behandelt dies als flache heterogene Liste. Verschiedene Spalten basieren auf dem Typ jedes Prinzipals.  <br/> Bei den meisten dieser Prinzipale handelt es sich um zwischengespeicherte Kopien von Objekten, die in Active Directory gespeichert sind. Das Erstellen der zwischengespeicherten Kopie in der Prinzipal Tabelle dieser Active Directory-Objekte wird als Bereitstellung bezeichnet.  <br/> Einige Prinzipale werden aggressiver als andere erstellt, und einige Active Directory-Objekte werden insgesamt ignoriert.  <br/> |
|[tblPrincipalAffiliations](tblprincipalaffiliations.md) <br/> |Enthält Haupt Zuordnungen, die Mitgliedschaften in Active Directory-Sicherheitsgruppen, Active Directory-Container usw. beschreiben.  <br/> |
|[tblNode](tblnode.md) <br/> |Enthält den Kategorie-Knoten, wie in der Systemsteuerung verwaltet.  <br/> |
|[tblRoleType](tblroletype.md) <br/> |Enthält Rollentypen und die zugehörigen Berechtigungssätze. Diese Nachschlagetabelle ist statisch.  <br/> |
|[tblScopePrincipal](tblscopeprincipal.md) <br/> |Enthält Bereiche, die Knoten zugewiesen sind.  <br/> |
|[tblPrincipalRole](tblprincipalrole.md) <br/> |Enthält Rollen, die Knoten zugewiesen sind.  <br/> |
|[tblSiopWhiteList](tblsiopwhitelist.md) <br/> |Enthält die registrierten Add-Ins, die Knoten zugeordnet werden können.  <br/> |
|[tblEnumAttribute](tblenumattribute.md) <br/> |Enthält nur die hartcodierten "Sichtbarkeits-" und "Verhalten"-Attribute, die in der tblNode-Tabelle verwendet werden.  <br/> |
|[tblEnumValue](tblenumvalue.md) <br/> |Enthält die Werte der hartcodierten "Visibility"-und "Behavior"-Attribute, die in der tblNode-Tabelle verwendet werden.  <br/> |
   
## <a name="invites-chats-and-other-client-support"></a>Einladungen, Chats und andere Client Unterstützung

|**Tabelle**|**Beschreibung**|
|:-----|:-----|
|[tblPrincipalInvites](tblprincipalinvites.md) <br/> |Enthält Einladungen für alle bereitgestellten Benutzer im System für alle Knoten, bei denen die automatische Einladung aktiviert ist.  <br/> |
|[tblChat](tblchat.md) <br/> |Enthält alle Chatnachrichten.  <br/> |
|[tblLastInviteId](tbllastinviteid.md) <br/> |Enthält die letzte Einladungs-ID, die für jeden Benutzer generiert (und in der tblPrincipalInvites-Tabelle verwendet) wurde.  <br/> |
|[tblLastChatId](tbllastchatid.md) <br/> |Enthält die letzte Chat-ID, die für jeden Benutzer generiert (und in der tblChat-Tabelle verwendet) wurde.  <br/> |
|[tblPreference](tblpreference.md) <br/> |Enthält Benutzer-Client-Einstellungen (nur von Legacy-Clients verwendet).  <br/> |
|[tblFileToken](tblfiletoken.md) <br/> |Enthält temporäre Token für Datei Übertragungs Zwecke. Jedes Mal, wenn eine Datei hochgeladen oder heruntergeladen wird, generiert der beständige Chat Dienst ein Token, das der Client für den Zugriff auf den Webdienst-Dateispeicher verwendet.  <br/> |
   
## <a name="server-support"></a>Serverunterstützung

|**Tabelle**|**Beschreibung**|
|:-----|:-----|
|[tblServerIdentity](tblserveridentity.md) <br/> |Enthält die aktiven Server im Server Pool für beständigen Chat.  <br/> |
|[tblAdminLock](tbladminlock.md) <br/> |Enthält die administratorsperre zum Ausführen einiger Administrator Befehle. Der systemrevision-Eintrag in der tblSystemRevision-Tabelle wird nach jeder Version der Sperre inkrementiert.  <br/> |
|[tblSystemRevision](tblsystemrevision.md) <br/> |Enthält den Eintrag für die Revisionsnummer (zusammen mit der tblAdminLock-Tabelle), um die Konsistenz auf mehreren Servern zu erreichen.  <br/> |
|[tblActivePeers](tblactivepeers.md) <br/> |Enthält aktuelle Peer-to-Peer-Verbindungen zwischen beständigen Chat Diensten.  <br/> |
|[tblConfig](tblconfig.md) <br/> |Enthält die Konfiguration des beständigen Chat Servers, die nicht unterstützt wird.  <br/> |
   

