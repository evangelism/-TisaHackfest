# Создание прототипа решения на базе Azure Web App с бэкендом и синхронизацией с Dynamics CRM Online

Во время Хакфеста инжинеры Microsoft вместе с разработчиками из компании ТИСА создали протоип решения автоматизированной системы продажи квартир для риэлторов с бэекндом в Dynamics CRM.
В процессе создания прототипа были выполнены следующие задачи:

- предложена архитектура решения, готового выдержать высокие нагрузки и при этом быть актуальной
- синхронизация данных в систему из Dynamics CRM и из системы в Dynamics CRM
- проверена возможность использования для задач обратной синхронизации Azure Functions и Logiс Apps




## Профиль партнёра






Tisa is an ISV. They use Dynamics CRM to create and sell solutions to real estate developers (who build apartment buildings) to automate sells. As other part of their business they maintain web site (from 1998 developed on ASP) to help connect Realtors/Agents and Developers to sell flats. The hackfest was around to create a new web site for those purposes. It should be well designed ready to scale, integrated with Dynamics CRM, Dynamics CRM Online. 
The web site should enable Agents/Retailers to make reservations for an apartment via an Azure Web Apps. The property developers put information about the units that are available and their prices to Dynamics CRM and Tisa pulls from Dynamics and places it into Azure SQL Database. For making reservations, an agent can look through the buildings that are available and book an apartment.  This pushed an event to another CRM database that is handled via a Logic App that orchestrates the reservation process.
Learnings & Processes 
1.	We had developed a working prototype in the first day. Azure Web App pull the data from Dynamics CRM, and put the reservation message to the Azure Queue. Then we tried 2 types of integration: a) Logic App take the message from the queue and put to Dynamics CRM b) Azure Functions take message from the queue and write to log.
2.	Second day we focus on Data Sync layer. Pull the date from Dynamics CRM and put it to the Azure SQL Database. We tried 2 ways of integrations: a) Logic Apps b) Web Jobs
Logic App trigger doesn’t fire when we add a record to the Dynamics CRM and we can’t make it workable.

For Web Job we had successfully prototype the process of pulling data from Dynamics CRM to Azure SQL Database 

During the hackfest the partner achieved all the expected results and ready to start develop the new solution with Azure. 
