# SQL_NULL

there is no nvl in mySQL
ifnull() and is null statement work here in MySQL!


* Syntax

        gender = IFNULL('F', gander) 

        倘若 gender is null 則 gender = 'F'
        若 gender 不為 null 則 gender


        句子則為 is null || is not null
        
* SQL Example

        CREATE DEFINER=`root`@`localhost` PROCEDURE `uspTest5_Case_Sw`(
                userId int
        )
        BEGIN

                select UserId, 
                        case Level
                                when 0 then 'bT'
                    when 1 then 'dM'
                    when 2 then 'mM'
                    when 3 then 'uM'
                    when 4 then 'Up'
                    else 'Exception'
                        End, ParentUserId, RealName
                from Reseller;

        END

* SQL Script

        CREATE PROCEDURE `uspUserRequest`(
            UId int,
            IN joinAppId int
        )
        BEGIN

            declare tamp int;
            set tamp = ifnull(null, joinAppId);     /* ifnull function */

          if joinAppId is null then     /* is null statement*/

            select * from user_request_join as urj
                where urj.userId = UId;

          else

            select * from user_request_join as urj
            where urj.userId = UId and urj.UserJoinAppId = tamp_iui;

          end if;

        END
