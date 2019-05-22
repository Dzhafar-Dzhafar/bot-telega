# bot-telega
calculator
package PACKAGE_NAME;

import org.telegram.telegrambots.api.objects.Update;
import org.telegram.telegrambots.bots.TelegramLongPollingBot;

import javax.script.ScriptEngine;
import javax.script.ScriptEngineManager;
import javax.script.ScriptException;

public class bot1 extends TelegramLongPollingBot {
private static long chat_id;
    @Override
    public void onUpdateReceived(Update update) {
     chat_id = update.getMessage().setChatId(chat_id);
     String text = update.getMassege().getText();
       onUpdateReceived();
       try {
           sendMassage.setText("the accepted information"+text);
           execute(sendMassege);
           sendMassage.setText("the analysis of the arrived information"+String.valueOF(getMsq (text)));
           execute(sendMassege);
       }
       catch (TelegramApiException e) {
       e.printStackTrace();
       }
    }   
    private float getMsq(String msq){
        try {
            ScriptEngine engine = new ScriptEngineManager().getEngineByName(shortName:"JavaScript");//support of a script for java (ScriptEngine)
            return Float.valueOF(engine.eval(msg).toString());
        }catch (ScriptException e){
            return 0;
        }
    }
  /*  @Override
    public void onUpdateReceived(Update update) {

    }

    @Override
    public String getBotUsername() {
        return null;
    }

    @Override
    public String getBotToken() {
        return null;
    }
}
