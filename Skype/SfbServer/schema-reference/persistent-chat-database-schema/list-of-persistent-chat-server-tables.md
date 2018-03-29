---
title: Liste der Tabellen für den Server für beständigen Chat
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 10/20/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 26c9e271-3516-4d90-b930-70fec4e359ea
description: Das Datenbankschema beständigen Chat besteht aus den folgenden Tabellen.
ms.openlocfilehash: d9a00095cb18e63cc29e16ae66e608127afad606
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/28/2018
---
# <a name="list-of-persistent-chat-server-tables"></a>Liste der Tabellen für den Server für beständigen Chat
 
Das Datenbankschema beständigen Chat besteht aus den folgenden Tabellen.
  
## <a name="active-directory-sync"></a>Active Directory-Synchronisierung

|**Tabelle**|**Beschreibung**|
|:-----|:-----|
|["tbladcookie"](tbladcookie.md) <br/> |Enthält die aktuellen Cookies Synchronisierung Lightweight Directory Access Protocol (LDAP). Jede Zeile entspricht einer Active Directory-Domänendienste-Domäne, der Persistent Chat Server aktiv auf Änderungen überwacht wird. (Nur Active Directory-Domänen, die für Persistent Chat Server relevant sind, werden in dieser Tabelle dargestellt.)  <br/> |
|[Principalmemberdifference](tblprincipalmemberdifference.md) <br/> |Enthält Änderungen der Gruppenmitgliedschaften (sowohl hinzugefügte als auch entfernte Mitglieder), die noch nicht von der späteren synchronisierungsschritten der Active Directory verarbeitet wurden und ist einer der temporären Tabellen (zusammen mit TblADUpdates-Tabelle), die im ersten Schritt der Active Directory-Synchronisierung verwendet wird.  <br/> Mitgliedschaftsänderungen gespeichert und/oder verarbeitet, oder nur für Gruppen, die bereits in der TblPrincipal-Tabelle oder die aufgelisteten haben Mitglieder aufgelistet sind.  <br/> |
|[tblADUpdates](tbladupdates.md) <br/> |Enthält Änderungen an Active Directory Domain Services, die von den späteren Schritten für die Active Directory-Synchronisierung noch nicht verarbeitet wurden und kann einen der temporären Tabellen (zusammen mit der Principalmemberdifference-Tabelle), die im ersten Schritt der Active Directory verwendet wird Synchronisieren.  <br/> Änderungen an Active Directory gespeichert und/oder verarbeitet, oder beides trifft nur für Prinzipale, die bereits in der TblPrincipal-Tabelle aufgelistet sind.  <br/> |
|["tblprincipalmembers"](tblprincipalmembers.md) <br/> |Enthält prinzipalmitgliedschaften.  <br/> |
|["tblprincipalmeta"](tblprincipalmeta.md) <br/> |Enthält die Prinzipale, die aus Active Directory aktualisiert werden müssen.  <br/> |
|[Skippedaffiliations](tblskippedaffiliations.md) <br/> |Enthält zugehörigkeiten, die in der Regel aufgrund von Active Directory-Zugriffsfehlern aus irgendeinem Grund nicht aktualisiert werden konnten.  <br/> In dieser Tabelle wird nur zu Informationszwecken. Der Inhalt wird nicht verwendet.  <br/> Die Prinzipale mit zugehörigkeiten, die nicht ordnungsgemäß aktualisiert werden konnten, werden in der TblPrincipalMeta-Tabelle gespeichert und bei Gelegenheit aktualisiert werden müssen.  <br/> |
   
## <a name="principals-affiliations-nodes-scopes-and-roles"></a>Prinzipale, Zugehörigkeiten, Knoten, Bereiche und Rollen

|**Tabelle**|**Beschreibung**|
|:-----|:-----|
|["tblprincipaltype"](tblprincipaltype.md) <br/> |Enthält Prinzipaltypen zur Kategorisierung in der TblPrincipal-Tabelle. In dieser Tabelle sind statisch. Beim Erstellen der Datenbank eingerichtet ist, und wird nicht geändert.  <br/> |
|[tblPrincipal](tblprincipal.md) <br/> |Enthält alle Prinzipale (Benutzer, Ordner, Gruppen und usw.). Persistent Chat Server behandelt dies als flache heterogenen Liste. Verschiedene Spalten basieren auf den Typ des jeweiligen Hauptbenutzer.  <br/> Die meisten dieser Prinzipale sind zwischengespeicherte Kopien von Objekten in Active Directory gespeichert. Erstellen der zwischengespeicherten Kopie in der Principal-Tabelle dieser Active Directory-Objekte wird als provisioning bezeichnet.  <br/> Einige Prinzipale werden Prinzipalen erstellt, und einige Active Directory-Objekte werden vollständig ignoriert.  <br/> |
|[tblPrincipalAffiliations](tblprincipalaffiliations.md) <br/> |Enthält die prinzipalzuordnungen, die Mitgliedschaften in Active Directory-Sicherheitsgruppen, Active Directory-Containern und So weiter beschreiben.  <br/> |
|[tblNode](tblnode.md) <br/> |Enthält den Kategorieknoten, wie in der Systemsteuerung verwaltet.  <br/> |
|["tblroletype"](tblroletype.md) <br/> |Enthält Rollentypen und deren zugeordneten Berechtigung festgelegt. Diese Nachschlagetabelle ist statisch.  <br/> |
|[in "tblscopeprincipal"](tblscopeprincipal.md) <br/> |Enthält Bereiche, die Knoten zugewiesen.  <br/> |
|[tblPrincipalRole](tblprincipalrole.md) <br/> |Enthält Rollen, die Knoten zugewiesen sind.  <br/> |
|[tblSiopWhiteList](tblsiopwhitelist.md) <br/> |Enthält die registrierte Add-Ins, die mit Knoten verknüpft werden können.  <br/> |
|[Enumattribute](tblenumattribute.md) <br/> |Enthält nur die hartcodierten "Visibility" und "Behavior" Attribute, die in der TblNode-Tabelle verwendet werden.  <br/> |
|[tblEnumValue](tblenumvalue.md) <br/> |Enthält die Werte der hartcodierten "Visibility" und "Behavior"-Attribute, die in der TblNode-Tabelle verwendet werden.  <br/> |
   
## <a name="invites-chats-and-other-client-support"></a>Einladungen, Chats und sonstige Clientunterstützung

|**Tabelle**|**Beschreibung**|
|:-----|:-----|
|[tblPrincipalInvites](tblprincipalinvites.md) <br/> |Enthält Einladungen für alle bereitgestellten Benutzer im System für alle Knoten mit aktivierter automatischer Einladung.  <br/> |
|[tblChat](tblchat.md) <br/> |Enthält alle Chatnachrichten.  <br/> |
|["tbllastinviteid"](tbllastinviteid.md) <br/> |Enthält die letzte einladungs-ID, die generierte (und in der TblPrincipalInvites-Tabelle verwendete) für jeden Benutzer.  <br/> |
|["lastchatid"](tbllastchatid.md) <br/> |Enthält die letzte Chat-ID, die generierte (und in der TblChat-Tabelle verwendete) für jeden Benutzer.  <br/> |
|[tblPreference](tblpreference.md) <br/> |Enthält benutzerclienteinstellungen (nur von Legacyclients verwendet).  <br/> |
|[tblFileToken](tblfiletoken.md) <br/> |Enthält temporäre Token für die Dateiübertragung. Jedes Mal eine Datei hochgeladen oder heruntergeladen, generiert der Persistent Chat-Dienst ein Token, das der Client verwendet, um auf den Dateispeicher für Web-Service zuzugreifen.  <br/> |
   
## <a name="server-support"></a>Serverunterstützung

|**Tabelle**|**Beschreibung**|
|:-----|:-----|
|[tblServerIdentity](tblserveridentity.md) <br/> |Enthält die aktiven Server im Pool Persistent Chat Server.  <br/> |
|[tblAdminLock](tbladminlock.md) <br/> |Enthält die Administratorsperre, um Administratorbefehle. Der Eintrag in der Tabelle "tblsystemrevision" Revision wird nach jeder Freigabe der Sperre erhöht.  <br/> |
|["tblsystemrevision"](tblsystemrevision.md) <br/> |Enthält den revisionsnummerneintrag (zusammen mit der Adminlock-Tabelle) verwendet für die Einhaltung der Konsistenz bei mehreren Servern.  <br/> |
|[tblActivePeers](tblactivepeers.md) <br/> |Enthält aktuelle Peer-zu-Peer-Verbindungen zwischen Persistent Chat-Dienste.  <br/> |
|[tblConfig](tblconfig.md) <br/> |Enthält die Persistent Chat Server nicht unterstützte Konfiguration.  <br/> |
   

