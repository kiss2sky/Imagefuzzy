package com.example.imagefuzzy;

import java.util.Random;

import android.content.Context;
import android.graphics.Bitmap;
import android.graphics.BitmapFactory;
import android.view.LayoutInflater;
import android.view.View;
import android.view.ViewGroup;
import android.view.animation.AlphaAnimation;
import android.view.animation.Animation;
import android.view.animation.Animation.AnimationListener;
import android.widget.AbsListView;
import android.widget.BaseAdapter;
import android.widget.ImageView;

public class GridviewAdapter extends BaseAdapter {

    private Context context;
    private int[]   res_img   = { R.drawable.ic_welcome_photo_1, R.drawable.ic_welcome_photo_2, R.drawable.ic_welcome_photo_3, R.drawable.ic_welcome_photo_4, R.drawable.ic_welcome_photo_5,
            R.drawable.ic_welcome_photo_6, R.drawable.ic_welcome_photo_7, R.drawable.ic_welcome_photo_8, R.drawable.ic_welcome_photo_9, R.drawable.ic_welcome_photo_10, R.drawable.ic_welcome_photo_11,
            R.drawable.ic_welcome_photo_12, R.drawable.ic_welcome_photo_13, R.drawable.ic_welcome_photo_14, R.drawable.ic_welcome_photo_15 };
    public int      MAX_WIDTH = 160;
    private int     dd        = 1;
    private int     ss        = -1;

    // private Animation animation1 = new AlphaAnimation(0.6f, 0.0f);
    // private Animation animation2 = new AlphaAnimation(0.0f, 0.6f);

    public GridviewAdapter(Context context) {
        super();
        this.context = context;
        MAX_WIDTH = ScreenUtils.getScreenW() / 3;
        System.out.println("========" + MAX_WIDTH);
    }

    public int getCount() {
        // TODO Auto-generated method stub
        return res_img.length;
    }

    @Override
    public Integer getItem(int position) {
        // TODO Auto-generated method stub
        return res_img[position];
    }

    @Override
    public long getItemId(int position) {
        // TODO Auto-generated method stub
        return position;
    }

    @Override
    public View getView(int position, View convertView, ViewGroup parent) {
        if (convertView == null) {
            convertView = LayoutInflater.from(context).inflate(R.layout.gv_item, parent, false);
            AbsListView.LayoutParams param = new AbsListView.LayoutParams(MAX_WIDTH, MAX_WIDTH);
            // RelativeLayout.LayoutParams param = (RelativeLayout.LayoutParams) convertView.getLayoutParams();
            // param.width = MAX_WIDTH;
            // param.height = MAX_WIDTH;
            convertView.setLayoutParams(param);
        }
        ImageView img_pic = ViewHolder.get(convertView, R.id.iv_1);
        final View view1 = ViewHolder.get(convertView, R.id.view_1);
        Bitmap srcBitmap = BitmapFactory.decodeResource(context.getResources(), getItem(position));
        img_pic.setImageBitmap(srcBitmap);
        if (position == dd) {

            // handler.sendEmptyMessageDelayed(1, 3500);
            Animation animation1 = new AlphaAnimation(1.0f, 0.0f);

            animation1.setDuration(5000);
            // 动画效果从XMl文件中定义
            // Animation animation = AnimationUtils.loadAnimation(this, R.anim.alpha);
            view1.setAnimation(animation1);
            animation1.setAnimationListener(new AnimationListener() {

                @Override
                public void onAnimationStart(Animation animation) {
                    // TODO Auto-generated method stub

                }

                @Override
                public void onAnimationRepeat(Animation animation) {
                    // TODO Auto-generated method stub

                }

                @Override
                public void onAnimationEnd(Animation animation) {
                    ss = dd;
                    dd = new Random().nextInt(getCount());
                    System.out.println("==========" + dd);
                    notifyDataSetChanged();
                }
            });
        }
        if (ss != -1 && position == ss) {
            Animation animation2 = new AlphaAnimation(0.0f, 1.0f);
            animation2.setDuration(3500);
            view1.setAnimation(animation2);
        }
        // img_pic.setBackgroundDrawable(context.getResources().getDrawable(getItem(position)));
        return convertView;
    }

}
