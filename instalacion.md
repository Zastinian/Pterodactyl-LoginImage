Abre /var/www/pterodactyl/resources/scripts/components/auth/LoginFormContainer.tsx

Pon debajo de import tw from 'twin.macro';

import { loginimage } from '../../../../public/hedystia/loginimage';

Busca

<Form {...props} ref={ref}>
            <div css={tw`md:flex w-full bg-white shadow-lg rounded-lg p-6 md:pl-0 mx-1`}>
                <div css={tw`flex-none select-none mb-6 md:mb-0 self-center`}>
                    <img src={'/assets/svgs/pterodactyl.svg'} css={tw`block w-48 md:w-64 mx-auto`}/>
                </div>
                <div css={tw`flex-1`}>
                    {props.children}
                </div>
            </div>
        </Form>

Remplázalo por

<Form {...props} ref={ref}>
            <div css={tw`md:flex w-full bg-white shadow-lg rounded-lg p-6 md:pl-0 mx-1`}>
                <div css={tw`flex-none select-none mb-6 md:mb-0 self-center`}>
                    <img src={loginimage} css={tw`block w-48 md:w-64 mx-auto`}/>
                </div>
                <div css={tw`flex-1`}>
                    {props.children}
                </div>
            </div>
        </Form>

Como poner el logo personalizado

Abre /var/www/pterodactyl/public/hedystia/loginimage.tsx

Busca
export const loginimage = "https://cdn.discordapp.com/attachments/851919671878746112/989747075312922695/ptero1.png";

Reemplaza el link por la imagen que quiera como logo

https://cdn.discordapp.com/attachments/851919671878746112/989747075312922695/ptero1.png

Comandos finales (SÓLO PROBADOS EN UBUNTU, PUEDE QUE NO FUNCIONEN EN OTRO SISTEMA OPERATIVO):

cd /var/www/pterodactyl
php artisan down
php artisan migrate --seed --force
yarn install
yarn build:production
php artisan config:cache
php artisan view:cache
php artisan queue:restart
php artisan up

Una vez puesto, si no carga hay que usar control + f5 3 o 4 veces para recargar la caché de la página y cargue correctamente.

Si tienes alguna duda, puedes contactar conmigo en el siguiente servidor de discord:

https://discord.gg/aXvuUpvRQs
