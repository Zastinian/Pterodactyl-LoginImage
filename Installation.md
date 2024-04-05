Open /var/www/pterodactyl/resources/scripts/components/auth/LoginFormContainer.tsx

Add below import tw from 'twin.macro';

import { loginimage } from '../../../../public/hedystia/loginimage';

Search

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

Replace it with

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

How to place a custom logo

Open /var/www/pterodactyl/public/hedystia/loginimage.tsx

Search
export const loginimage = "https://hedystia.com/favicon.ico";

Replace the link with the image you want as logo

https://hedystia.com/favicon.ico

Final commands (ONLY TESTED ON UBUNTU, MAY NOT WORK ON OTHER OPERATING SYSTEMS):

cd /var/www/pterodactyl
php artisan down
php artisan migrate --seed --force
yarn install
yarn build:production
php artisan config:cache
php artisan view:cache
php artisan queue:restart
php artisan up

Once set, if it does not load, use control + f5 3 or 4 times to reload the page cache and load correctly.

If you have any questions, you can contact me at the following discord server:

https://discord.gg/aXvuUpvRQs
