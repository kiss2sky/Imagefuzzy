package com.example.imagefuzzy;

import android.app.Activity;
import android.os.Bundle;
import android.view.MotionEvent;
import android.view.View;
import android.view.View.OnTouchListener;
import android.widget.GridView;

public class WelcomeActivity extends Activity {

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_welcome);
        ScreenUtils.initScreen(this);
        GridView gv_img = (GridView) findViewById(R.id.gv_img);
        GridviewAdapter adapter = new GridviewAdapter(this);
        gv_img.setAdapter(adapter);
        gv_img.setOnTouchListener(new OnTouchListener() {
            @Override
            public boolean onTouch(View v, MotionEvent event) {
                return MotionEvent.ACTION_MOVE == event.getAction() ? true : false;
            }
        });
    }

}

