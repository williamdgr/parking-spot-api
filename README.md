# Parking-Spot-Api

## Para iniciar é preciso inserir no banco as Roles

INSERT INTO public.tb_role(	role_id, role_name)	VALUES ('40ed8970-20b4-11ed-861d-0242ac120002', 'ROLE_ADMIN');

INSERT INTO public.tb_role(	role_id, role_name)	VALUES ('464c5202-20b4-11ed-861d-0242ac120002', 'ROLE_USER');

## Para criar um usuário é preciso pegar a senha  criptografada no log inicial e salvar um usuário no banco com esta senha. Deixei um insert de usuário inicial pronto, pois não temos endpoint para cadastrar usuário.

INSERT INTO public.tb_user(	userid, password, username)
VALUES ('08c5df40-1e55-11ed-861d-0242ac120002',
'$2a$10$rLY9hFgGynMh6oB2EIhaF.BdS8wiP4/UiscxU2geED9mIHvLZHzsi',
'william');

## Por fim vinculamos o usuário às roles, seguem os inserts..

-- Vincula o usuário com a ROLE_ADMIN

INSERT INTO public.tb_users_roles(
user_id, role_id)
VALUES ('08c5df40-1e55-11ed-861d-0242ac120002', '40ed8970-20b4-11ed-861d-0242ac120002');

-- Vincula o usuário com a ROLE_USER

INSERT INTO public.tb_users_roles(
user_id, role_id)
VALUES ('08c5df40-1e55-11ed-861d-0242ac120002', '464c5202-20b4-11ed-861d-0242ac120002');