# SQL_NULL
ifnull()

gender = IFNULL('F', gander) 

倘若 gender is null 則 gender = 'F'
若 gender 不為 null 則 gender


句子則為 is null || is not null

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
