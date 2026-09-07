import asyncio
from aiogram import Bot, Dispatcher, types
from aiogram.filters import Command

TOKEN = 8612756919:AAE29QgZfrs0n1KaMQt8vAtA4OsRaWfxSeA
ADMIN_USERNAME = "mando2008"
ADMIN_ID = 8737142541 

bot = Bot(token=TOKEN)
dp = Dispatcher()

@dp.message(Command("start"))
async def start(message: types.Message):
    text = f"""أهلا يا {message.from_user.first_name} في سوق ماندو الرسمي 🔥

🛒 بيع وشراء:
• قنوات واتساب وتيليجرام
• حسابات تيك توك وانستا
• حسابات ببجي وفري فاير وجميع الالعاب

🛡️ بضمان الادمن @mando2008"""

    kb = types.InlineKeyboardMarkup(inline_keyboard=[
        [types.InlineKeyboardButton(text="🛒 تصفح السوق", callback_data="market")],
        [types.InlineKeyboardButton(text="➕ عرض منتج للبيع", callback_data="sell")],
        [types.InlineKeyboardButton(text="💬 تواصل مع الادمن", url=f"https://t.me/{ADMIN_USERNAME}")],
        [types.InlineKeyboardButton(text="📢 قناة الاثباتات", url=f"https://t.me/{ADMIN_USERNAME}")]
    ])
    await message.answer(text, reply_markup=kb)

@dp.callback_query(lambda c: c.data == "market")
async def market(callback: types.CallbackQuery):
    kb = types.InlineKeyboardMarkup(inline_keyboard=[
        [types.InlineKeyboardButton(text="📱 واتساب", callback_data="cat_wa")],
        [types.InlineKeyboardButton(text="✈️ تيليجرام", callback_data="cat_tg")],
        [types.InlineKeyboardButton(text="🎮 حسابات العاب", callback_data="cat_games")],
        [types.InlineKeyboardButton(text="👤 سوشيال", callback_data="cat_social")],
        [types.InlineKeyboardButton(text="⬅️ رجوع", callback_data="back")]
    ])
    await callback.message.edit_text("اختار القسم اللي عاوزه:", reply_markup=kb)

# --- نظام تواصل مع الادمن الاحترافي ---
@dp.message(lambda m: m.text == "💬 تواصل مع الادمن" or "الادمن" in m.text)
async def ask_message(message: types.Message):
    await message.answer("✍️ ابعت رسالتك دلوقتي وهتوصل للادمن @mando2008 مباشرة:")

async def main():
    await dp.start_polling(bot)

if name == "main":
    asyncio.run(main())
