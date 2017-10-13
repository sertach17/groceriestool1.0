# groceriestool1.0
package torrez.groceriestool2;

import android.support.v7.app.AppCompatActivity;
import android.os.Bundle;
import android.view.View;
import android.widget.EditText;
import android.widget.TextView;

import static java.lang.Math.round;
import static torrez.groceriestool2.R.id.nikolGrandTotal;
import static torrez.groceriestool2.R.id.sergioGrandTotal;
import static torrez.groceriestool2.R.id.tereGrandTotal;
import static torrez.groceriestool2.R.id.tony;
import static torrez.groceriestool2.R.id.tonyGrandTotal;
import static torrez.groceriestool2.R.id.totalPersonal;
import static torrez.groceriestool2.R.id.wal;

public class MainActivity extends AppCompatActivity {
    EditText walmartarriba, bjarriba, ctownarriba, tonyspendarriba, sergiospendarriba, terespendarriba,
            nikolspendarriba;

    TextView totalSpendarriba, totalPersonalarriba, sergioGrandTotalarriba, tereGrandTotalarriba,
            tonyGrandTotalarriba, nikolGrandTotalarriba, divisionCuatroidarriba;

    float walm, bjes, ctownes, tonyspends, sergiospends, terespends, nikolspends;

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);
        walmartarriba = (EditText) findViewById(R.id.wal);
        bjarriba = (EditText) findViewById(R.id.bj);
        ctownarriba = (EditText) findViewById(R.id.ct);
        tonyspendarriba = (EditText) findViewById(tony);
        sergiospendarriba = (EditText) findViewById(R.id.sergio);
        terespendarriba = (EditText) findViewById(R.id.tere);
        nikolspendarriba = (EditText) findViewById(R.id.nikol);
        totalSpendarriba = (TextView) findViewById(R.id.totalSpend);
        totalPersonalarriba = (TextView) findViewById(totalPersonal);
        sergioGrandTotalarriba = (TextView) findViewById(sergioGrandTotal);
        tereGrandTotalarriba = (TextView) findViewById(tereGrandTotal);
        tonyGrandTotalarriba = (TextView) findViewById(tonyGrandTotal);
        nikolGrandTotalarriba = (TextView) findViewById(nikolGrandTotal);

    }

    public void onButtonClick(View v) {
        walm = Float.parseFloat(walmartarriba.getText().toString());
        bjes = Float.parseFloat(bjarriba.getText().toString());
        ctownes = Float.parseFloat(ctownarriba.getText().toString());
        tonyspends = Float.parseFloat(tonyspendarriba.getText().toString());
        sergiospends = Float.parseFloat(sergiospendarriba.getText().toString());
        terespends = Float.parseFloat(terespendarriba.getText().toString());
        nikolspends = Float.parseFloat(nikolspendarriba.getText().toString());

        float spendsResult = walm + bjes + ctownes;
        float totalPersonales = tonyspends + sergiospends + terespends + nikolspends;
        float grandtotal = spendsResult - totalPersonales;
        float divisionCuatro = ((grandtotal / 4));
        float tonyYsergio = ((divisionCuatro / 2) + divisionCuatro);
        float sergioGrandTotales = tonyYsergio + sergiospends;
        float tereGrandTotales = divisionCuatro + terespends;
        float tonyGrandTotales = tonyYsergio + tonyspends;
        float nikolGrandTotales = nikolspends;
        totalSpendarriba.setText(Float.toString(spendsResult));
        totalPersonalarriba.setText(Float.toString(totalPersonales));
        sergioGrandTotalarriba.setText(Float.toString(sergioGrandTotales));
        tereGrandTotalarriba.setText(Float.toString(tereGrandTotales));
        tonyGrandTotalarriba.setText(Float.toString(tonyGrandTotales));
        nikolGrandTotalarriba.setText(Float.toString(nikolGrandTotales));
    }

}
